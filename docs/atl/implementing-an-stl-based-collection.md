---
title: "STL ベースのコレクションの実装 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICollectionOnSTLImpl インターフェイス"
ms.assetid: 6d49f819-1957-4813-b074-3f12c494d8ca
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# STL ベースのコレクションの実装
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL は、標準テンプレート ライブラリの \(STL\) のオブジェクト ベースのコレクションのインターフェイスを実装できるように `ICollectionOnSTLImpl` のインターフェイスを提供します。  このクラスの機能を理解するには、読み取り専用コレクションによって目指されるオートメーション クライアントを実行するには、このクラスを使用する簡単な例の \(以下\) で動作します。  
  
 サンプル コードは [ATLCollections sample](../top/visual-cpp-samples.md)からです。  
  
 この手順を完了するには、:  
  
-   [新しい簡単なオブジェクトを生成します。](#vccongenerating_an_object)。  
  
-   生成されたインターフェイスの[IDL ファイルを編集します。](#vcconedit_the_idl)。  
  
-   コレクション項目を格納、およびどのように、COM クライアントに公開する方法を記述 する[5 個の typedef を作成します。](#vcconstorage_and_exposure_typedefs) はインターフェイスです。  
  
-   [コピー ポリシー クラスの 2 種類の typedef を作成します。](#vcconcopy_classes)。  
  
-   [列挙子とコレクションの実装の typedef を作成します。](#vcconenumeration_and_collection)。  
  
-   [コレクションの typedef を使用するためにウィザードで生成された C\+\+ コードを編集します。](#vcconedit_the_generated_code)。  
  
-   [コレクションを作成するコードを追加します。](#vcconpopulate_the_collection)。  
  
##  <a name="vccongenerating_an_object"></a> 新しいシンプル オブジェクトの生成  
 新しいプロジェクトを、アプリケーション設定の下の属性ボックスがオフになっていることを確認して作成します。  ATL クラスの追加\]ダイアログ ボックスを使用して、`Words`という単純なオブジェクトを生成するためのシンプル オブジェクト ウィザードを追加します。  `IWords` と呼ばれるデュアル インターフェイスが生成されることを確認します。  生成されたクラスのオブジェクトは、\(文字列\) のコレクションを表すために使用されます。  
  
##  <a name="vcconedit_the_idl"></a> IDL ファイルの編集  
 次に、IDL ファイルを開き、次に示すように、読み取り専用コレクションのインターフェイスに `IWords` を、の一に必要なプロパティを 3 つ追加します:  
  
 [!code-cpp[NVC_ATL_COM#24](../atl/codesnippet/CPP/implementing-an-stl-based-collection_1.idl)]  
  
 これは、デザインされるところでオートメーション クライアントを持つ読み取り専用コレクション インターフェイスの標準形式です。  このインターフェイス定義の番号が付けられるコメントは次のようにコメントに対応しています:  
  
1.  コレクションのインターフェイスは通常オートメーション クライアントが **IDispatch::Invoke**によって `_NewEnum` のプロパティにアクセスできるため、階層です。  ただし、オートメーション クライアントは、vtable を使用して残りのメソッドにアクセスできます。つまり、デュアル インターフェイスは、ディスパッチ インターフェイスに必要です。  
  
2.  デュアル インターフェイスまたはディスパッチ インターフェイスが、実行時 \(つまり、**IDispatch::Invoke**して、メソッドまたはプロパティを提供しません\) に拡張であるか、または **nonextensible** の定義に属性を適用する必要があります。  この属性は、コンパイル時に完全なコード検証を実行することをオートメーション クライアントができます。  この場合、拡張インターフェイスは必要ではありません。  
  
3.  適切な DISPID は、オートメーション クライアントにこのプロパティを使用できるように重要です。  **DISPID\_NEWENUM**に 1 二つのアンダースコアがあることに注意してください\)。  
  
4.  **\[アイテム\]** のプロパティの DISPID として値を指定できます。  ただし、**\[アイテム\]** は、通常はコレクション、既定のプロパティに **DISPID\_VALUE** を使用します。  これは、オートメーション クライアントが明示的に表示せずにプロパティを示すことができます。  
  
5.  **\[アイテム\]** のプロパティの戻り値に使用するデータ型は、COM クライアントに関する限りでは、コレクションに格納されている項目の型です。  インターフェイスは文字列を返すため、文字列型、`BSTR`を標準の COM を使用する必要があります。  次に示すように別の形式のデータを内部的に格納できます。  
  
6.  **Count** のプロパティの DISPID に使用する値は、完全に任意です。  このプロパティの標準 DISPID がありません。  
  
##  <a name="vcconstorage_and_exposure_typedefs"></a> ストレージと公開の typedef の作成  
 コレクションのインターフェイスを定義したら、データの格納方法、およびデータが列挙子によって公開されるかを決定する必要があります。  
  
 これらの質問に対する答えは、新しく作成したクラスのヘッダー ファイルの先頭部分に追加できるいくつかの typedef の形式で指定できます:  
  
 [!code-cpp[NVC_ATL_COM#25](../atl/codesnippet/CPP/implementing-an-stl-based-collection_2.h)]  
  
 この場合、**std::string**、.の **std::vector** としてデータを格納します。  **std::vector** は、マネージ配列のようにして、STL コンテナー クラスです。  **std::string** は、標準 C\+\+ ライブラリの文字列クラスです。  これらのクラスは、文字列のコレクションを使用しやすくなります。  
  
 Visual Basic のサポートがこのインターフェイスの成功に不可欠であるため、`_NewEnum` のプロパティによって返される列挙子は **IEnumVARIANT** のインターフェイスをサポートしている必要があります。  これは、Visual Basic によって認識される唯一の列挙子インターフェイスです。  
  
##  <a name="vcconcopy_classes"></a> コピー ポリシー クラスの typedef の作成  
 、今まで作成した typedef は、列挙子とコレクションで使用されるトランスポート クラス用の typedef を作成する必要があるすべての情報を提供します:  
  
 [!code-cpp[NVC_ATL_COM#26](../atl/codesnippet/CPP/implementing-an-stl-based-collection_3.h)]  
  
 この例では、[ATLCollections](../top/visual-cpp-samples.md) の例から、VCUE\_Copy.h と VCUE\_CopyString.h で定義されるカスタム `GenericCopy` のクラスを使用できます。  他のコードにこのクラスを使用して独自のコレクションで使用されるデータ型をサポートするために `GenericCopy` の特殊化を定義する必要があります。  詳細については、[ATL コピー ポリシー クラス](../Topic/ATL%20Copy%20Policy%20Classes.md)を参照してください。  
  
##  <a name="vcconenumeration_and_collection"></a> 列挙体、およびコレクションの typedef の作成  
 これで、この状態の `CComEnumOnSTL` と `ICollectionOnSTLImpl` のクラスを特化するために必要なすべてのテンプレート パラメーターは typedef の形式で指定されています。  特化の使用を簡単にするためには、次に示すように、2 種類の詳細に typedef を作成する:  
  
 [!code-cpp[NVC_ATL_COM#27](../atl/codesnippet/CPP/implementing-an-stl-based-collection_4.h)]  
  
 これで `CollectionType` は、前に定義された `IWords` のインターフェイスを実装し、その列挙子をサポート **IEnumVARIANT**提供する `ICollectionOnSTLImpl` の特化型のシノニムです。  
  
##  <a name="vcconedit_the_generated_code"></a> ウィザードで生成されたコードの編集  
 これは、次に示すように `IWords`ではなく `CollectionType` の typedef で表される、インターフェイスの実装から `CWords` を取得する必要があります:  
  
 [!code-cpp[NVC_ATL_COM#28](../atl/codesnippet/CPP/implementing-an-stl-based-collection_5.h)]  
  
##  <a name="vcconpopulate_the_collection"></a> コードをコレクションに項目を追加するコードの追加  
 後は、データのベクターに読み込みます。  この簡単な例では、クラスのコンストラクターのコレクションにいくつかの単語を追加できます:  
  
 [!code-cpp[NVC_ATL_COM#29](../atl/codesnippet/CPP/implementing-an-stl-based-collection_6.h)]  
  
 これで、任意のクライアントとのコードをテストできます。  
  
## 参照  
 [コレクションと列挙子](../atl/atl-collections-and-enumerators.md)   
 [ATLCollections sample](../top/visual-cpp-samples.md)   
 [ATL のコピー ポリシー クラス](../Topic/ATL%20Copy%20Policy%20Classes.md)