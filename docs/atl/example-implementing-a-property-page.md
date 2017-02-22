---
title: "例 : プロパティ ページの実装 | Microsoft Docs"
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
  - "プロパティ ページ, 実装"
ms.assetid: c30b67fe-ce08-4249-ae29-f3060fa8d61e
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 例 : プロパティ ページの実装
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

この例では、\(変更することを許可します\) [ドキュメント クラス](../mfc/document-classes.md) のインターフェイスのプロパティを表示するプロパティ ページをビルドする方法を示します。  このインターフェイスは、Visual Studio の [Common Environment Object Model Examples](../Topic/Common%20Environment%20Object%20Model%20Examples.md) のドキュメントによって \(正しいインターフェイスをサポートする範囲オブジェクトが取得されます\) その場所から処理するか、作成するプロパティ ページが気遣わないが公開されます。  
  
 この例では [ATLPages サンプル](../top/visual-cpp-samples.md)に基づいています。  
  
 この例を実行するには、:  
  
-   クラスの追加\]ダイアログ ボックスと ATL プロパティ ページ ウィザードを使用して[ATL プロパティ ページのクラスを追加します。](#vcconusing_the_atl_object_wizard)。  
  
-   **\[ドキュメント\]** のインターフェイスを実装プロパティの新しいコントロールを追加して、[ダイアログ リソースを編集します。](#vcconediting_the_dialog_resource)。  
  
-   プロパティ ページのサイトを保持[追加のメッセージ ハンドラー](#vcconadding_message_handlers) は、変更のユーザーが行った知らせました。  
  
-   [ハウスキーピング](#vcconhousekeeping) のセクションの `#import` のあるステートメントおよび typedef を追加します。  
  
-   プロパティ ページに渡されるオブジェクトを検証する[IPropertyPageImpl::SetObjects をオーバーライドします](#vcconoverriding_ipropertypageimpl_setobjects)。  
  
-   プロパティ ページのインターフェイスを初期化する[オーバーライド IPropertyPageImpl::Activate](#vcconoverriding_ipropertypageimpl_activate)。  
  
-   最新のプロパティの値を持つオブジェクトを更新する[オーバーライド IPropertyPageImpl::Apply](#vcconoverride_ipropertypageimpl_apply)。  
  
-   単純なヘルパー オブジェクトを作成して[プロパティ ページを表示します。](#vccontesting_the_property_page)。  
  
-   プロパティ ページをテストする[マクロを作成します。](#vcconcreating_a_macro)。  
  
##  <a name="vcconusing_the_atl_object_wizard"></a> ATL プロパティ ページ クラスの追加  
 最初に、`ATLPages7`という DLL のサーバーの新しい ATL プロジェクトを作成します。  これは、プロパティ ページを生成するために [&#91;ATL プロパティ ページ ウィザード&#93;](../atl/reference/atl-property-page-wizard.md) を使用します。  プロパティ ページに **DocProperties** の **\[短い名前\]** を付けると **\[文字列\]** は、プロジェクトのプロパティ ページ固有の項目、次の表に示すように、ページに切り替えます。  
  
|項目|値|  
|--------|-------|  
|タイトル|TextDocument|  
|\[ドキュメント文字列\]|VCUE TextDocument のプロパティ|  
|ヘルプファイル|*blank*|  
  
 **IPropertyPage::GetPageInfo**を呼び出したときにプロパティ ページのコンテナーにウィザードのこのページの設定値を返すこと。  後で発生するコンテナーに依存する、ユーザーがそのページを識別するためにが何が文字列に使用します。  タイトルは、通常、ページの上部にあるタブに表示され、\(標準のプロパティ フレームはこの文字列をまったく使用せずに\) ドキュメントの文字列がステータス バーやツール ヒントに表示される場合があります。  
  
> [!NOTE]
>  ウィザードによって、プロジェクト設定で次のように文字列リソース格納する文字列。  、ページのコードが生成された後にこの情報を変更する必要がある場合、リソース エディターを使用して簡単にこれらの文字列を編集できます。  
  
 、プロパティ ページを生成するウィザードがに設定されたクリック **OK**。  
  
##  <a name="vcconediting_the_dialog_resource"></a> ダイアログ リソースの編集  
 独自のプロパティ ページが生成したので、ページを表すダイアログ リソースにいくつかのコントロールを追加する必要があります。  エディット ボックス、静的テキスト コントロールとチェック ボックスを追加し、次に示すように ID を設定します:  
  
 ![ダイアログ リソースを編集します](../atl/media/ppgresourcelabeled.gif "PPGResourceLabeled")  
  
 これらのコントロールをドキュメントと読み取り専用ステータスのファイル名を表示するために使用されます。  
  
> [!NOTE]
>  ダイアログ リソースは、フレームまたはコマンド ボタンが含まれていませんが、意図した可能性がある記録された外観があります。  これらの機能は [OleCreatePropertyFrame](http://msdn.microsoft.com/library/windows/desktop/ms678437)を呼び出すことで作成されるようなプロパティ ページ フレームによって提供されます。  
  
##  <a name="vcconadding_message_handlers"></a> メッセージ ハンドラーを追加できます。  
 コントロールを使用すると、コントロール内のいずれかの値も、ページのダーティな状態を更新するためのメッセージ ハンドラーを追加できます:  
  
 [!code-cpp[NVC_ATL_Windowing#73](../atl/codesnippet/CPP/example-implementing-a-property-page_1.h)]  
  
 このコードは [IPropertyPageImpl::SetDirty](../Topic/IPropertyPageImpl::SetDirty.md)のページのサイトを通知する呼び出しによって加えられたエディット コントロールまたはチェック ボックスへの変更にページを変更した応答します。  一般に、ページのサイトではプロパティ ページの **\[適用\]** フレームのボタンを有効または無効にするとします。  
  
> [!NOTE]
>  独自のプロパティ ページで、変更されていないプロパティが更新されることを防ぐために、プロパティがユーザーによって変更された正確に追跡する必要がある場合があります。  元のプロパティ値を追跡し、UI からの現在の値と比較して、変更を適用時間である場合、この例のコードを実装します。  
  
##  <a name="vcconhousekeeping"></a> ハウスキーピング  
 これは、コンパイラが **\[ドキュメント\]** のインターフェイスを認識するように DocProperties.h に `#import` のいくつかのステートメントを追加します:  
  
 [!code-cpp[NVC_ATL_Windowing#74](../atl/codesnippet/CPP/example-implementing-a-property-page_2.h)]  
  
 また `IPropertyPageImpl` の基本クラスを参照する必要があります。; **CDocProperties** のクラスに次の `typedef` を追加します:  
  
 [!code-cpp[NVC_ATL_Windowing#75](../atl/codesnippet/CPP/example-implementing-a-property-page_3.h)]  
  
##  <a name="vcconoverriding_ipropertypageimpl_setobjects"></a> オーバーライドの IPropertyPageImpl::SetObjects  
 でオーバーライドする必要がある `IPropertyPageImpl` の最初のメソッドは、[SetObjects](../Topic/IPropertyPageImpl::SetObjects.md)です。  単一のオブジェクトのみが渡されたことと、が使用する **\[ドキュメント\]** のインターフェイスをサポートするチェックするコードを追加します:  
  
 [!code-cpp[NVC_ATL_Windowing#76](../atl/codesnippet/CPP/example-implementing-a-property-page_4.h)]  
  
> [!NOTE]
>  ユーザーは、オブジェクトのファイル名を設定できるようにするため、ページの単一オブジェクトのみをサポートすると便利です— 1 ファイルで、1 の位置にあることができます。  
  
##  <a name="vcconoverriding_ipropertypageimpl_activate"></a> オーバーライドの IPropertyPageImpl::Activate  
 次の手順では、ページが最初に作成されたとき、基になるオブジェクトのプロパティの値を持つプロパティ ページを初期化することです。  
  
 この場合、ページのユーザーが変更を追加すると、比較の初期プロパティ値を使用するため、クラスに次のメンバーを追加する必要があります:  
  
 [!code-cpp[NVC_ATL_Windowing#77](../atl/codesnippet/CPP/example-implementing-a-property-page_5.h)]  
  
 [&#91;ライセンス認証&#93;](../Topic/IPropertyPageImpl::Activate.md) のメソッドの基本クラスの実装は、ダイアログ ボックスやコントロールを作成する必要があり、このメソッドをオーバーライドし、基本クラスを呼び出した後、独自の初期化を追加できます:  
  
 [!code-cpp[NVC_ATL_Windowing#78](../atl/codesnippet/CPP/example-implementing-a-property-page_6.h)]  
  
 このコードはことで、プロパティの取得に **\[ドキュメント\]** のインターフェイスの COM メソッドを使用します。  をユーザーにプロパティ値を表示することを [CDialogImpl](../Topic/CDialogImpl%20Class.md) と基本クラスによって提供される Win32 API のラッパーを使用します。  
  
##  <a name="vcconoverride_ipropertypageimpl_apply"></a> オーバーライドの IPropertyPageImpl::Apply  
 ユーザーがオブジェクトへの変更を適用するときに、プロパティ ページのサイト [&#91;適用&#93;](../Topic/IPropertyPageImpl::Apply.md) のメソッドを呼び出します。  これは **\[ライセンス認証\]** のコードの逆にする場所です— **\[ライセンス認証\]** がオブジェクトから値を受け取り、プロパティ ページのコントロールに対し、Enter **\[適用\]** は、プロパティ ページのコントロールから値を受け取り、オブジェクトにキーを押します。  
  
 [!code-cpp[NVC_ATL_Windowing#79](../atl/codesnippet/CPP/example-implementing-a-property-page_7.h)]  
  
> [!NOTE]
>  この実装の先頭に [m\_bDirty](../Topic/IPropertyPageImpl::m_bDirty.md) に対するチェックは **\[適用\]** が複数回呼び出すとオブジェクトの不要な更新を避ける最初のチェックがあります。  変更のみ **\[ドキュメント\]**のメソッド呼び出しで発生することを確認するプロパティ値のそれぞれに対して、チェックがあります。  
  
> [!NOTE]
>  読み取り専用プロパティとして公開**\[ドキュメント\]** の **FullName**。  変更したプロパティ ページへの変更に基づいてドキュメントのファイル名を更新するには別の名前でファイルを保存するに **上書き保存** のメソッドを使用する必要があります。  したがって、プロパティ ページのコードのプロパティを取得または設定することに制限する必要はありません。  
  
##  <a name="vccontesting_the_property_page"></a> プロパティ ページの表示  
 このページを表示するには、単純なヘルパー オブジェクトを作成する必要があります。  ヘルパー オブジェクトは、一つのオブジェクトに接続される単一のページを表示するための **OleCreatePropertyFrame** API を簡単にするメソッドを提供します。  このヘルパーは、Visual Basic で使用できるように設計されています。  
  
 新しいクラスを生成し、短い形式の名前として `Helper` を使用するに [クラスの追加&#93;ダイアログ ボックス](../ide/add-class-dialog-box.md) と [&#91;ATL シンプル オブジェクト ウィザード&#93;](../atl/reference/atl-simple-object-wizard.md) を使用します。  作成される、次の表に示すようにメソッドを追加します。  
  
|項目|値|  
|--------|-------|  
|メソッド名|`ShowPage`|  
|パラメーター|`[in] BSTR bstrCaption, [in] BSTR bstrID, [in] IUnknown* pUnk`|  
  
 `bstrCaption` のパラメーターは、ダイアログ ボックスのタイトルとして表示されるキャプションです。  `bstrID` のパラメーターは、表示するプロパティ ページの CLSID または ProgID を表す文字列です。  `pUnk` のパラメーターは、プロパティがプロパティ ページで構成されるオブジェクトの `IUnknown` のポインターです。  
  
 次に示すようにメソッドを実装する:  
  
 [!code-cpp[NVC_ATL_Windowing#80](../atl/codesnippet/CPP/example-implementing-a-property-page_8.cpp)]  
  
##  <a name="vcconcreating_a_macro"></a> マクロの作成  
 プロジェクトをビルドして Visual Studio の開発環境で作成し、実行できる簡単なマクロを使用してプロパティ ページ、およびヘルパー オブジェクトをテストできます。  このマクロは、ヘルパー オブジェクトを作成し、Visual Studio のエディターで現在アクティブなドキュメントの **DocProperties** のプロパティ ページと **IUnknown** のポインターの ProgID を使用して **ShowPage** のメソッドを呼び出します。  このマクロに必要なコードは次のように示しています:  
  
```  
Imports EnvDTE  
Imports System.Diagnostics  
  
Public Module AtlPages  
  
    Public Sub Test()  
        Dim Helper  
        Helper = CreateObject("ATLPages7.Helper.1")  
  
        On Error Resume Next  
        Helper.ShowPage( _  
            ActiveDocument.Name, _  
            "ATLPages7Lib.DocumentProperties.1", _  
            DTE.ActiveDocument _  
            )  
    End Sub  
  
End Module  
```  
  
 このマクロを実行すると、現在アクティブなテキスト ドキュメントのファイル名と読み取り専用の状態を示すプロパティ ページが表示されます。  ドキュメントの読み取り専用状態は、開発環境のドキュメントへの書き込み機能のみを反映します; これは、ディスク上のファイルの読み取り専用属性には影響しません。  
  
## 参照  
 [プロパティ ページ](../atl/atl-com-property-pages.md)   
 [ATLPages サンプル](../top/visual-cpp-samples.md)