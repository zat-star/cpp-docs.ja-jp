---
title: "型システム (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/03/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b67bee8a-b526-4872-969e-ef22724e88fe
caps.latest.revision: 28
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 28
---
# 型システム (C++/CX)
[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] アーキテクチャを使用すると、[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]、Visual Basic、Visual C\# および JavaScript を使用して、Windows API に直接アクセスしたり、他の [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] アプリやコンポーネントと相互運用したりするアプリやコンポーネントを作成できます。 C\+\+ で記述された [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリは、CPU で直接実行するネイティブ コードにコンパイルされます。 C\# または Visual Basic で記述された [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリケーションは、Microsoft Intermediate Language \(MSIL\) にコンパイルされ、共通言語ランタイム \(CLR\) で実行されます。 JavaScript で記述された [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリケーションは、実行時環境で実行されます。[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] オペレーティング システムのコンポーネント自体が、C\+\+ で記述され、ネイティブ コードとして実行されます。 これらのすべてのコンポーネントおよび [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリケーションは、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] アプリケーション バイナリ インターフェイス \(ABI\) を通じて直接やり取りします。  
  
 最新の C\+\+ 表現で [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] のサポートを有効にするため、Microsoft は [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) を作成しました。[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] は、組み込み基本型、および C\+\+ アプリケーションやコンポーネントが ABI 間で他の言語で記述されたアプリケーションと通信するのを可能にする [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] の基本型の実装を提供します。 任意の [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型を使用するか、他の [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリケーションやコンポーネントが使用できるクラス、構造体、インターフェイス、および他のユーザー定義型を作成できます。[!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] で記述された [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] アプリケーションは、パブリック アクセシビリティを持たないかぎり、正規の C\+\+ クラスおよび構造体も使用できます。  
  
 C\+\+\/CX 言語プロジェクションと内部動作の詳しい説明については、次のブログ記事を参照してください。  
  
1.  [C\+\+\/CX パート 0\/\[n\]: はじめに](http://blogs.msdn.com/b/vcblog/archive/2012/08/29/cxxcxpart00anintroduction.aspx)  
  
2.  [C\+\+\/CX パート 0\/\[n\]: はじめに](http://blogs.msdn.com/b/vcblog/archive/2012/08/29/cxxcxpart00anintroduction.aspx)  
  
3.  [C\+\+\/CX パート 2\/\[n\]: ハット記号が付いた型](http://blogs.msdn.com/b/vcblog/archive/2012/09/17/cxxcxpart02typesthatwearhats.aspx)  
  
4.  [C\+\+\/CX パート 3\/\[n\]: 作成中](http://blogs.msdn.com/b/vcblog/archive/2012/10/05/cxxcxpart03underconstruction.aspx)  
  
5.  [C\+\+\/CX パート 4\/\[n\]: 静的メンバー関数](http://blogs.msdn.com/b/vcblog/archive/2012/10/19/cxxcxpart04staticmemberfunctions.aspx)  
  
## Windows メタデータ \(.winmd\) ファイル  
 C\+\+ で記述された [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリケーションをコンパイルすると、コンパイラは、ネイティブのマシン語コードの実行可能ファイルを生成します。また、クラス、構造体、列挙体、インターフェイス、パラメーター化されたインターフェイス、およびデリゲートなど、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] パブリック型の記述を含む個別の Windows メタデータ \(.winmd\) も生成します。 メタデータの形式は、.NET Framework アセンブリで使用される形式に似ています。  C\+\+ コンポーネントでは、.winmd ファイルにはメタデータのみ含まれています。実行可能コードは、別個のファイルに存在します。 Windows に含まれる [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネントがこれに当てはまります。 WinMD ファイルの名前はソース コードのルート名前空間のプレフィックスに一致またはそれ自体である必要があります。 \(.NET Framework 言語の場合、.winmd ファイルには、.NET Framework アセンブリのようにコードとメタデータの両方が含まれます。\)  
  
 .winmd ファイルのメタデータは、コードの公開されたサーフェイスを表します。 公開された型は、他のアプリケーションが記述された言語にかかわりなく、他の [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] に表示されます。 したがって、メタデータ、または公開されたコードには、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型システムによって指定された型だけを含めることができます。 標準クラス、配列、テンプレートまたは STL コンテナーなど、C\+\+ 固有の言語構造体は、メタデータで発行できません。理由は、JavaScript または C\# クライアント アプリケーションが対処できないからです。  
  
 型またはメソッドがメタデータに表示されるかどうかは、適用されるアクセシビリティ修飾子によって異なります。 型を表示するには、型が名前空間で宣言され、パブリックとして宣言されている必要があります。 非パブリックの ref クラスは、コード内で内部ヘルパー型として許可されています。これは、メタデータでは表示されません。 パブリック ref クラスでも、すべてのメンバーが表示されるとは限りません。 次の表は、パブリック ref クラスでの C\+\+ アクセス指定子の関係、および [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] メタデータの可視性の一覧を示しています。  
  
|||  
|-|-|  
|**メタデータで公開**|**メタデータで非公開**|  
|public|private|  
|protected|internal|  
|public protected|private protected|  
  
 .winmd ファイルの内容を表示するために、**オブジェクト ブラウザー**を使用できます。 Windows に含まれる [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネントは、Windows.winmd ファイルにあります。 default.winmd ファイルには [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] で使用される基本型が含まれ、platform.winmd には Platform 名前空間の追加型が含まれます。 既定では、これらの 3 個の .winmd ファイルは、[!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリケーションのすべての C\+\+ プロジェクトに含まれます。  
  
> [!TIP]
>  [Platform::Collections 名前空間](../cppcx/platform-collections-namespace.md) 型は、パブリックではないので、.winmd ファイルには表示されません。 これらは、`Windows::Foundation::Collections` で定義されているインターフェイスのプライベート C\+\+ 固有の実装です。 JavaScript または C\# で記述された [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] アプリケーションは、[Platform::Collections::Vector クラス](../cppcx/platform-collections-vector-class.md) が何かを認識しませんが、`Windows::Foundation::Collections::IVector` を使用することはできます。`Platform::Collections` 型は、collection.h で定義されます。  
  
## [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] での [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] 型システム  
 以下のセクションでは、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型システムの主な機能、および [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] でのそれらの機能のサポートについて説明します。  
  
### 名前空間  
 すべての [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型を 1 つの名前空間内で宣言する必要があります。Windows API 自体は、名前空間ごとに構成されています。 .winmd ファイルには、ルート名前空間と同じ名前が必要です。 たとえば、A.B.C.MyClass という名前のクラスは、A.winmd または A.B.winmd または A.B.C.winmd という名前のメタデータ ファイルで定義されている場合のみインスタンス化できます。 DLL の名前が .winmd ファイル名と一致する必要はありません。  
  
 Windows API 自体が、名前空間ごとに構成された、十分にファクタリングされたクラス ライブラリとして再開発されました。  すべての [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネントは、Windows.\* 名前空間で宣言されています。  
  
 詳細については、「[名前空間と型の参照範囲](../cppcx/namespaces-and-type-visibility-c-cx.md)」を参照してください。  
  
### 基本型  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] は、基本型である UInt8、Int16、UInt16、UInt32、Int32、UInt64、Int64、Single、Double、Char16、Boolean、および String を定義します。[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] は、uint16、uint32、uint64、int16、int32、int64、float32、float64、および char16 として、既定の名前空間の基本的な数値型をサポートしています。 ブール値と文字列も、Platform 名前空間で定義されます。  
  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] は、`unsigned char` と等価の uint8 も定義します。uint8 は、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] ではサポートされておらず、パブリック API では使用できません。  
  
 基本型を null 許容にするには、[Platform::IBox インターフェイス](../cppcx/platform-ibox-interface.md)にラップします。 詳細については、「[値クラスと構造体](../cppcx/value-classes-and-structs-c-cx.md)」を参照してください。  
  
 基本型の詳細については、「[基本的な型](../cppcx/fundamental-types-c-cx.md)」を参照してください。  
  
### 文字列  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 文字列は、16 ビット UNICODE 文字列の変更できないシーケンスです。[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 文字列は、`Platform::String^` として投影されます。 このクラスは、文字列の作成、操作、および `wchar_t` への変換 \(およびその逆\) のためのメソッドを提供します。  
  
 詳細については、「[文字列](../cppcx/strings-c-cx.md)」を参照してください。  
  
### 配列  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] は、任意の型の一次元の配列をサポートしています。 配列の配列はサポートされていません。[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] では、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 配列は [Platform::Array クラス](../cppcx/platform-array-class.md) として投影されます。  
  
 詳細については、「[Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)」を参照してください。  
  
### Ref クラスと構造体  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] クラスは、参照によりコピーされるため、[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] では ref クラスまたは ref 構造体として投影されます。 ref クラスと ref 構造体のメモリ管理は、参照カウントによって透過的に処理されます。 オブジェクトへの最後の参照がスコープ外に出ると、オブジェクトは破棄されます。 ref クラスまたは ref 構造体では、次のことができます。  
  
-   コンストラクター、メソッド、プロパティ、およびイベントをメンバーとして格納できます。 これらのメンバーには、パブリック、プライベート、プロテクト、または内部のアクセシビリティを指定できます。  
  
-   プライベートの入れ子になった構造体、列挙体、またはクラス定義を格納できます。  
  
-   1 つの基底クラスから直接継承し、任意の数のインターフェイスを実装できます。 ref クラスは、いずれも [Platform::Object クラス](../cppcx/platform-object-class.md) に暗黙的に変換可能で、[Object::ToString](../cppcx/object-tostring-method-c-cx.md) などの仮想メソッドをオーバーライドできます。  
  
 パブリック コンストラクターを持つ ref クラスは、さらに派生されることを防ぐために、シール済みとして宣言する必要があります。  
  
 詳細については、「[Ref クラスと構造体](../cppcx/ref-classes-and-structs-c-cx.md)」を参照してください。  
  
### 値クラスと構造体  
 値クラスまたは値の構造体は、基本的なデータ構造体を表し、フィールドのみ格納できます。フィールドには、値クラス、値構造体、または `Platform::String^` 型が含まれます。  値構造体と値クラスは、値によってコピーされます。  
  
 値構造体を null 許容にするには、IBox インターフェイスにラップします。  
  
 詳細については、「[値クラスと構造体](../cppcx/value-classes-and-structs-c-cx.md)」を参照してください。  
  
### 部分クラス  
 部分クラスの機能を使用して、1 つのクラスを複数のファイルに対して定義できます。 この機能は主に、XAML エディターなどのコード生成ツールで、編集するファイルにアクセスせずに 1 つのファイルを変更するために使用されます。  
  
 詳細については、「[部分クラス](../cppcx/partial-classes-c-cx.md)」を参照してください。  
  
### プロパティ  
 プロパティは任意の [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型のパブリック データ メンバーで、get メソッドと set メソッドのペアとして実装されます。 クライアント コードは、パブリック フィールドのようにプロパティにアクセスします。 カスタムの get または set コードを必要とするプロパティは、*trivial プロパティ*と呼ばれ、明示的な get または set メソッドを使用せずに宣言できます。  
  
 詳細については、「[プロパティ](../cppcx/properties-c-cx.md)」を参照してください。  
  
### [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] での [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] コレクション  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] は、各言語が独自の方法で実装する、コレクション型の一連のインターフェイスを定義します。[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] は、[Platform::Collections::Vector クラス](../cppcx/platform-collections-vector-class.md)、[Platform::Collections::Map クラス](../cppcx/platform-collections-map-class.md)、および対応する標準テンプレート ライブラリ \(STL\) と互換性がある他の関連する具象コレクション型の実装を提供します。  
  
 詳細については、「[コレクション](../cppcx/collections-c-cx.md)」を参照してください。  
  
### テンプレート ref クラス  
 プライベート ref クラスおよび内部 ref クラスは、テンプレート化および特化できます。  
  
 詳細については、「[テンプレート ref クラス](../cppcx/template-ref-classes-c-cx.md)」を参照してください。  
  
### インターフェイス  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] インターフェイスは、ref クラスまたは ref 構造体が、インターフェイスから継承する場合に実装する必要がある、一連のパブリック プロパティ、メソッド、およびイベントを定義します。  
  
 詳細については、「[インターフェイス](../cppcx/interfaces-c-cx.md)」を参照してください。  
  
### 列挙体  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] の列挙体クラスは、C\+\+ のスコープ列挙体に似ています。 基になる型は int32 です。\[Flags\] 属性が適用された場合、基になる型は uint32 です。  
  
 詳細については、「[列挙型](../cppcx/enums-c-cx.md)」を参照してください。  
  
### デリゲート  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] のデリゲートは、C\+\+ の std::function オブジェクトに似ています。 これは、互換性のあるシグニチャを持つクライアント提供関数を呼び出すために使用される、特殊な種類の ref クラスです。  デリゲートは、通常、イベントの型として [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] で使用されます。  
  
 詳細については、「[デリゲート](../cppcx/delegates-c-cx.md)」を参照してください。  
  
### 例外  
 C\+\+\/CX では、カスタムの例外の種類、[std::exception](~/standard-library/exception-class.md) 型、および [Platform::Exception](../cppcx/platform-exception-class.md) 型をキャッチできます。  
  
 詳細については、「[例外](../cppcx/exceptions-c-cx.md)」を参照してください。  
  
### イベント  
 イベントは、型がデリゲート型の、ref クラスまたは ref 構造体のパブリック メンバーです。 イベントに対して可能なのは、所有するクラスによる呼び出し \(つまり、発生\) だけです。 ただし、クライアント コードが独自の関数を提供することはできます。それらの関数はイベント ハンドラーと呼ばれ、所有クラスでイベントが発生したときに呼び出されます。  
  
 詳細については、「[イベント](../cppcx/events-c-cx.md)」を参照してください。  
  
### キャスト  
 C\+\+\/CX は、標準 C\+\+ のキャスト演算子 [static\_cast](../cpp/static-cast-operator.md)、[dynamic\_cast](../cpp/dynamic-cast-operator.md)、および [reinterpret\_cast](../cpp/reinterpret-cast-operator.md) をサポートし、C\+\+\/CX に固有の [safe\_cast](~/windows/safe-cast-cpp-component-extensions.md) 演算子もサポートします。  
  
 詳細については、「[キャスト](../cppcx/casting-c-cx.md)」を参照してください。  
  
### ボックス化  
 ボックス化された変数は、参照セマンティクスが必要な場合に参照型にラップされる値の型です。  
  
 詳細については、「[ボックス化とボックス化解除](../cppcx/boxing-c-cx.md)」を参照してください。  
  
### 属性  
 属性は、任意の [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型または型のメンバーに適用でき、実行時に検査できるメタデータ値です。[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] は、`Windows::Foundation::Metadata` 名前空間で一連の共通の属性を定義します。 パブリック インターフェイスのユーザー定義属性は、このリリースの [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] ではサポートされていません。  
  
## API の非推奨  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] のシステム型によって使用されるのと同じ属性を使用して、パブリック API に非推奨のマークを付ける方法について説明します。  
  
 詳細については、「[型およびメンバーの非推奨化](../cppcx/deprecating-types-and-members-c-cx.md)」を参照してください。  
  
## 参照  
 [Visual C\+\+ の言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)