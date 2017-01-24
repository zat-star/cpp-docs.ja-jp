---
title: "方法 : タイプ セーフなコレクションを作成する | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コレクション クラス, 派生 (非テンプレートから)"
  - "コレクション クラス, テンプレート ベースの"
  - "コレクション クラス, タイプ セーフ"
  - "シリアル化 [C++], コレクション クラス"
  - "SerializeElements 関数"
  - "シリアル化 (コレクション クラスの要素を)"
  - "タイプ セーフなコレクション"
ms.assetid: 7230b2db-4283-4083-b098-eb231bf5b89e
caps.latest.revision: 10
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法 : タイプ セーフなコレクションを作成する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、独自のデータ型のタイプ セーフなコレクションを設定する方法について説明します。  ここでは、次の内容について説明します。  
  
-   [タイプ セーフのテンプレート ベースのクラスを使用します。](#_core_using_template.2d.based_classes_for_type_safety)  
  
-   [ヘルパー関数の実装](#_core_implementing_helper_functions)  
  
-   [非テンプレート コレクション クラスを使用する](#_core_using_nontemplate_collection_classes)  
  
 Microsoft Foundation Class ライブラリには、C\+\+ テンプレートに基づいて定義済みのなタイプ セーフなコレクションを提供します。  これらのテンプレートであるため、これらのクラスは、非テンプレート クラスをこの目的で使用する場合には型キャストなしでタイプ セーフと使いやすさなどの追加作業が増しました。  MFC のサンプル [収集する](../top/visual-cpp-samples.md) アプリケーションは、MFC のテンプレート ベースのコレクション クラスの使用方法を示します。  通常、新しいコレクション コードを記述して、これらのクラスを使用します。  
  
##  <a name="_core_using_template.2d.based_classes_for_type_safety"></a> タイプ セーフのテンプレート ベースのクラスを使用します。  
  
#### テンプレート ベースのクラスを使用するには  
  
1.  コレクション クラスの型の変数を宣言します。  たとえば、次のようになります。  
  
     [!code-cpp[NVC_MFCCollections#7](../mfc/codesnippet/CPP/how-to-make-a-type-safe-collection_1.cpp)]  
  
2.  コレクション オブジェクトのメンバー関数を呼び出します。  たとえば、次のようになります。  
  
     [!code-cpp[NVC_MFCCollections#8](../mfc/codesnippet/CPP/how-to-make-a-type-safe-collection_2.cpp)]  
  
3.  必要に応じて、[ヘルパー関数](../mfc/reference/collection-class-helpers.md) と [SerializeElements](../Topic/SerializeElements.md)を実装してください。  これらの関数の実装の詳細については、「[ヘルパー関数の実装](#_core_implementing_helper_functions)」を参照してください。  
  
 この例では、整数のリストの宣言を示しています。  手順 1 の最初のパラメーターは、リストの要素として格納されたデータの型です。  2 番目のパラメーターは、データをどのように渡され、**追加** と `GetAt`などのコレクション クラスのメンバー関数から返すかどうかを指定します。  
  
##  <a name="_core_implementing_helper_functions"></a> ヘルパー関数の実装  
 、派生のコレクション クラスのために必要に応じてカスタマイズできるテンプレート ベースのコレクション クラス `CArray`、`CList`と `CMap` の使用 5 のグローバルなヘルパー関数。  これらのヘルパー関数については、*" MFC リファレンス"*の [コレクション クラスのヘルパー](../mfc/reference/collection-class-helpers.md) を参照してください。  シリアル化の関数の実装は、テンプレート ベースのコレクション クラスの主な用途に必要です。  
  
###  <a name="_core_serializing_elements"></a> 要素のシリアル化  
 `CArray`、`CList`と `CMap` クラスはコレクション要素を保存するか、アーカイブからの読み取りに `SerializeElements` を呼び出します。  
  
 `SerializeElements` ヘルパー関数の既定の実装は、オブジェクトのアーカイブからオブジェクトへの、読み取りをアーカイブにオブジェクトが格納されているか、アーカイブから取得されているかどうかビットごとのの書き込み、またはビットごとので描画します。  このアクションが適切でない場合 `SerializeElements` をオーバーライドします。  
  
 `CObject` からコレクションのストア オブジェクトの派生と、コレクション要素クラスの実装で `IMPLEMENT_SERIAL` マクロを使用すると、`CArchive` と `CObject`に組み込まれているシリアル化機能を使用する場合:  
  
 [!code-cpp[NVC_MFCCollections#9](../mfc/codesnippet/CPP/how-to-make-a-type-safe-collection_3.cpp)]  
  
 `CArchive` のオーバーロードされた出力ストリーム演算子は `CObject::Serialize` \(または **CPerson** のオブジェクトごとに、その関数のオーバーライドを呼び出します。  
  
##  <a name="_core_using_nontemplate_collection_classes"></a> 非テンプレート コレクション クラスを使用する  
 MFC は、MFC Version 1.0 で導入されたコレクション クラスをサポートします。  これらのクラスは、テンプレートに基づいていません。  これらがサポートされている型 `CObject*`、**UINT**、`DWORD`と `CString`のデータを格納するために使用できます。   \(`CObList`など\) `CObject`から派生される任意のオブジェクトのコレクションを保持するには、これらの定義済みのなコレクションを使用できます。  MFC は、**UINT** と void なポインター \(`void`保持する他の定義済みのなコレクションを\*\) などのプリミティブ型が用意されています。  ただし、通常は、多くの場合、特定のクラスとその派生クラスのオブジェクトを保持するために独自のタイプ セーフなコレクションを定義すると便利です。  テンプレートに基づいてコレクション クラスを使用するには、テンプレート ベースのクラスを使用するよりも多くの作業があることに注意してください。  
  
 非テンプレートのコレクションにタイプ セーフなコレクションを作成するには 2 とおりの方法があります。:  
  
1.  型キャストがある非テンプレートのコレクションを、必要な場合に使用します。  これは、より簡単な方法です。  
  
2.  から派生し、非テンプレートのタイプ セーフなコレクションを拡張します。  
  
#### 型キャストがある非テンプレートのコレクションを使用します。  
  
1.  非テンプレート クラスの 1 を、`CWordArray`など、直接使用します。  
  
     たとえば、`CWordArray` を作成し、32 ビット値を追加し、それを取得します。  この方法は何もありません。  一つ定義済みのな機能を使用します。  
  
     たとえば、オブジェクトを `CObject`から派生されて保持するために定義済みのなコレクションを、`CObList`などの同期プリミティブを使用できます。  `CObList` のコレクションは `CObject`へのポインターを保持するように定義されます。  一覧からオブジェクトを取得する場合、`CObList` 関数が `CObject`へのポインターを返すので、結果を適切な型にキャストしなければならない場合があります。  たとえば、`CObList` のコレクションで `CPerson` オブジェクトを保存すると、`CPerson` オブジェクトへのポインターである場合、取得する要素をキャストしなければなりません。  次の例では `CPerson` オブジェクトを保持するために `CObList` のコレクションを使用します:  
  
     [!code-cpp[NVC_MFCCollections#10](../mfc/codesnippet/CPP/how-to-make-a-type-safe-collection_4.cpp)]  
  
     定義済みのなコレクション型を使用したり、必要としてキャストするこの方法はコレクションのニーズの多くには十分な場合があります。  そのほかの機能やそのほかのタイプ セーフが必要な場合は、テンプレート ベースのクラスを使用するか、次の手順に従います。  
  
#### 非テンプレートのタイプ セーフなコレクションを拡張する派生し、  
  
1.  定義済みのな非テンプレート クラスの 1 つがから独自のコレクション クラスを派生してください。  
  
     クラスを派生する場合は、既存の関数にタイプ セーフなインターフェイスを提供するタイプ セーフなラッパー関数を追加できます。  
  
     たとえば、`CPerson` オブジェクトを保持するために `CObList` からリストを派生したら、次に示すように、ラッパー関数 `AddHeadPerson` と `GetHeadPerson`を追加する場合があります。  
  
     [!code-cpp[NVC_MFCCollections#11](../mfc/codesnippet/CPP/how-to-make-a-type-safe-collection_5.h)]  
  
     これらのラッパー関数を追加するタイプ セーフな方法を提供し、`CPerson` オブジェクトを派生から取得するように指定します。  単にカプセル化している型キャストを `GetHeadPerson` の関数でも参照できます。  
  
     また、拡張する新しい関数を定義することで、新しい機能を追加できるため、タイプ セーフなラッパーの既存の機能をラップしますではなく、コレクションの機能を紹介します。  たとえば、技術情報 [CObject のコレクション内のすべてのオブジェクトの削除](../Topic/Deleting%20All%20Objects%20in%20a%20CObject%20Collection.md)、リストのすべての含まれるオブジェクトを削除するための関数について説明します。  この関数は、メンバー関数として派生クラスに追加できます。  
  
## 参照  
 [コレクション クラス](../mfc/collections.md)