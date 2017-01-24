---
title: "MFC ActiveX コントロール : ActiveX コントロールのローカライズ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LocaleID"
  - "AfxOleRegisterTypeLib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LocaleID アンビエント プロパティ"
  - "ローカリゼーション, ActiveX コントロール"
  - "LOCALIZE サンプル [MFC]"
  - "MFC ActiveX コントロール, ローカライズ"
ms.assetid: a44b839a-c652-4ec5-b824-04392708a5f9
caps.latest.revision: 12
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC ActiveX コントロール : ActiveX コントロールのローカライズ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、ActiveX コントロールのインターフェイスをローカライズする方法について説明します。  
  
 国際市場に ActiveX コントロールを使用する場合は、コントロールをローカライズしたい場合があります。  Windows は、フランス語とドイツ語スウェーデン語を含む既定の英語以外に多くの言語をサポートします。  これは、インターフェイスが英語の一つだけコントロールの問題が発生します。  
  
 一般に、ActiveX コントロールは LocaleID のアンビエント プロパティにロケールを常に行う必要があります。  これには、次の 3 つの方法があります。  
  
-   LocaleID のアンビエント プロパティの現在の値に基づいて、必要に応じてリソースを、常に読み込んでください。  MFC ActiveX コントロールのサンプル [ローカライズしてください。](../top/visual-cpp-samples.md) はこの方法を使用します。  
  
-   最初のコントロールが、LocaleID のアンビエント プロパティに基づいて例に付けて、他のすべてのインスタンスで、それらのリソースを使用するときに、リソースを読み込んでください。  ここでは、この方法を示します。  
  
    > [!NOTE]
    >  これは、以降のインスタンスに別のロケールがある場合、場合によっては正しく機能しません。  
  
-   動的にコンテナーのロケールの適切なリソースを読み込むために **OnAmbientChanged** 通知関数を使用します。  
  
    > [!NOTE]
    >  これは、コントロールのように動作しますが、ランタイム DLL が動的に所有されたリソースは、LocaleID のアンビエント プロパティの変更を更新しません。  また、ActiveX コントロールのランタイム DLL はリソースのロケールを決定するためにスレッドのロケールを使用します。  
  
 ここからは、2 種類のローカライズの方法について説明します。  一つ目の方法 [コントロールのプログラミング インターフェイスをローカライズします](#_core_localizing_your_control.92.s_programmability_interface) \(プロパティ、メソッド、およびイベントの名前\)。  コンテナーのアンビエント LocaleID のプロパティを使用して、2 番目の方法 [コントロールのユーザー インターフェイスがローカライズします](#_core_localizing_the_control.92.s_user_interface)。  コントロールのローカリゼーションの例については、" MFC ActiveX コントロール [ローカライズしてください。](../top/visual-cpp-samples.md)サンプルを参照してください。  
  
##  <a name="_core_localizing_your_control.92.s_programmability_interface"></a> コントロールのプログラミング インターフェイスのローカライズ  
 コントロールのプログラミング インターフェイス \(書き込みプログラマに使用するインターフェイスをコントロール\) を使用するアプリケーションをローカライズした場合、各言語のコントロール .IDL ファイル \(コントロール タイプ ライブラリをビルドするためのスクリプト\) の変更後のバージョンを作成する必要があるサポートしようとします。  これには、コントロール プロパティの名前をローカライズする必要があるだけで済みます。  
  
 ローカライズされたコントロールを開発するときに、タイプ ライブラリのレベルに属性としてロケール ID を指定します。  たとえばフランス語でローカライズされるプロパティ名をタイプ ライブラリに変更する場合は、SAMPLE.IDL ファイルのコピーを作成し、SAMPLEFR.IDL を呼び出します。  次のようなファイルにロケール ID 属性 \(フランス語のロケール ID は 0x040c\) 追加する:  
  
 [!code-cpp[NVC_MFC_AxLoc#1](../mfc/codesnippet/CPP/mfc-activex-controls-localizing-an-activex-control_1.idl)]  
  
 SAMPLEFR.IDL プロパティ名をフランス語の等価に変更し、フランス語のタイプ ライブラリを生成するために、SAMPLEFR.TLB MKTYPLIB.EXE を使用します。  
  
 、複数のローカライズされるタイプ ライブラリを作成するには、プロジェクトにローカライズされた .IDL ファイルを追加し、自動的にビルドされます。  
  
#### 追加するには .IDL は ActiveX コントロール プロジェクト ファイルで  
  
1.  **プロジェクト** 、メニューの開く、コントロール プロジェクトで **\[既存のアイテムを追加\]** をクリックします。  
  
     **既存のアイテムを追加** ダイアログ ボックスが表示されます。  
  
2.  必要に応じて、表示にドライブとディレクトリを選択します。  
  
3.  **ファイルの種類** ボックスで、**\[すべてのファイル \(\*.\*\) \]** を選択します。  
  
4.  ファイル ボックスで、プロジェクトに挿入する .IDL ファイルをダブルクリックします。  
  
5.  必要なすべての .IDL ファイルを追加した場合は **開く** をクリックします。  
  
 ファイルがプロジェクトに追加されたので、他のプロジェクトのビルド時にビルドされます。  ローカライズされたタイプ ライブラリが現在の ActiveX コントロール プロジェクトのディレクトリにあります。  
  
 コード内で、内部プロパティ名は \(通常は英語\)、常に使用され、ローカライズされません。  これは、コントロールのディスパッチ マップ、所持品の swap 関数とプロパティ ページ ダイアログ データ エクスチェンジ コードが含まれています。  
  
 1 個のタイプ ライブラリ \(.TLB\) ファイルのみコントロールの実装 \(.OCX ファイル\) のリソースにバインドされる場合があります。  これは通常、標準化された \(通常、英語\) 名前のバージョンです。  コントロールのローカライズ バージョンを提供するには、同梱する既にバインドされてしまった\) と適切なロケールの .TLB .OCX \(既定 .TLB バージョンで必要があります。  これは、正しい .TLB が、既にバインドされてしまった .OCX 英語版のためだけに必要であることを意味します。  他のロケールでは、ローカライズされたタイプ ライブラリは、.OCX に付属する必要があります。  
  
 コントロールのクライアントがローカライズされたタイプ ライブラリを検索できることを確認するには、Windows のレジストリに typelib セクションでロケール固有 .TLB File を登録します。  [AfxOleRegisterTypeLib](../Topic/AfxOleRegisterTypeLib.md) 関数の 3 番目のパラメーター \(通常省略可能な\) 使用されます。  次の例では、ActiveX コントロールのフランス語のタイプ ライブラリを登録する:  
  
 [!code-cpp[NVC_MFC_AxLoc#2](../mfc/codesnippet/CPP/mfc-activex-controls-localizing-an-activex-control_2.cpp)]  
  
 コントロールを登録すると、`AfxOleRegisterTypeLib` 関数はコントロールとレジスタと自動的に同じディレクトリの指定 .TLB File を Windows 登録情報データベース内で検索します。  .TLB ファイルが見つからない場合、この関数は無効です。  
  
##  <a name="_core_localizing_the_control.92.s_user_interface"></a> コントロールのユーザー インターフェイスのローカライズ  
 コントロールのユーザー インターフェイスをローカライズするには、言語固有のリソース DLL にコントロールのユーザーが認識可能なすべてのリソース \(プロパティ ページとエラー メッセージなど\) を配置します。  ユーザーのロケールに適切な DLL は、コンテナーのアンビエント LocaleID のプロパティを使用できます。  
  
 次のコード例は特定のロケールのリソース DLL を検索して読み込むための 1 種類の方法を示しています。  この例の `GetLocalizedResourceHandle` と呼ばれるこのメンバー関数は、ActiveX コントロール クラスのメンバー関数である可能性があります:  
  
 [!code-cpp[NVC_MFC_AxLoc#3](../mfc/codesnippet/CPP/mfc-activex-controls-localizing-an-activex-control_3.cpp)]  
  
 副言語 ID は switch ステートメントの各ケース チェックインできるに特化されたローカリゼーションを用意することに注意してください。  この関数の例については、" MFC ActiveX コントロールのサンプル [ローカライズしてください。](../top/visual-cpp-samples.md)の `GetResourceHandle` 関数を参照してください。  
  
 コントロールがコンテナーに最初に読み込むと、ロケール ID を取得するために [COleControl::AmbientLocaleID](../Topic/COleControl::AmbientLocaleID.md) を呼び出すことができます。  コントロールが適切なリソース ライブラリを読み込む `GetLocalizedResourceHandle` 関数に返されたロケール ID 値を渡すことができます。  コントロールは [AfxSetResourceHandle](../Topic/AfxSetResourceHandle.md)に発生したハンドルがあれば、渡す必要があります:  
  
 [!code-cpp[NVC_MFC_AxLoc#4](../mfc/codesnippet/CPP/mfc-activex-controls-localizing-an-activex-control_4.cpp)]  
  
 [COleControl::OnSetClientSite](../Topic/COleControl::OnSetClientSite.md)のオーバーライドなどのコントロールのメンバー関数に上のコード サンプルを移動します。  また、`m_hResDLL` はコントロール クラスのメンバー変数。  
  
 コントロールのプロパティ ページをローカライズする場合、同様のロジックを使用できます。  プロパティ ページをローカライズするには、次の例のようなプロパティ ページの実装ファイルにコードを追加します。[COlePropertyPage::OnSetPageSite](../Topic/COlePropertyPage::OnSetPageSite.md)のオーバーライドで\) :  
  
 [!code-cpp[NVC_MFC_AxLoc#5](../mfc/codesnippet/CPP/mfc-activex-controls-localizing-an-activex-control_5.cpp)]  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)