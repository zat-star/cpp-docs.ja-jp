---
title: "MFC プログラムまたはコントロールのソース ファイルとヘッダー ファイル | Microsoft Docs"
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
  - "ファイルの種類 [C++], MFC ソースとヘッダー"
ms.assetid: f61419a8-bf69-4bbb-8f7c-1734be5e6db6
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC プログラムまたはコントロールのソース ファイルとヘッダー ファイル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio で MFC プロジェクトを作成すると、以下のファイルが作成されます。作成されるファイルは、プロジェクトに対して指定したオプションによって異なります。  たとえば、プロジェクトに *Projname*dlg.cpp ファイルと *Projname*dlg.h ファイルが作成されるのは、ダイアログ ベースのプロジェクトやクラスを作成した場合だけです。  
  
 これらのファイルはすべて、*Projname* ディレクトリ、およびソリューション エクスプローラーの \[ヘッダー ファイル\] \(.h ファイルの場合\) フォルダーか \[ソース ファイル\] \(.cpp ファイルの場合\) フォルダーにあります。  
  
|ファイル名|Description|  
|-----------|-----------------|  
|*Projname*.h|プログラムまたは DLL の主要なインクルード ファイル。  すべてのグローバル シンボルとほかのヘッダー ファイルの `#include` ディレクティブが記述されています。  `CWinApp` クラスから `CPrjnameApp` クラスを派生し、`InitInstance` メンバー関数を宣言します。  コントロールの場合、`CPrjnameApp` クラスは `COleControlModule` から派生します。|  
|*Projname*.cpp|プログラムの主要なソース ファイル。  `CWinApp` の派生クラスである `CPrjnameApp` クラスのオブジェクトが 1 つ生成され、メンバー関数 `InitInstance` がオーバーライドされます。<br /><br /> 実行可能ファイルの場合、`CPrjnameApp::InitInstance` はいくつかの処理を行います。  この関数は、ドキュメント テンプレートを登録してドキュメントとビューを結合し、主要なフレーム ウィンドウを作成し、空のドキュメントを作成します。アプリケーションのコマンド ライン引数でドキュメントが指定されている場合は、そのドキュメントを開きます。<br /><br /> DLL と ActiveX \(以前の OLE\) コントロールの場合、`CProjNameApp::InitInstance` は、`COleObjectFactory::RegisterAll` を呼び出してコントロールのオブジェクト ファクトリを OLE に登録し、`AfxOLEInit` を呼び出します。  また、メンバー関数 `CProjNameApp::ExitInstance` を使用して **AfxOleTerm** を呼び出し、コントロールをメモリからアンロードします。<br /><br /> また、このファイルは `DllRegisterServer` 関数と `DllUnregisterServer` 関数を実装して、Windows NT レジストリ情報のコントロールの登録と登録解除を行います。|  
|*Projname*ctrl.h、*Projname*ctrl.cpp|`CProjnameCtrl` クラスを宣言して実装するファイル。  `CProjnameCtrl` は `COleControl` の派生クラスであり、コントロールの初期化、描画、およびシリアル化 \(読み込みと保存\) を行うスケルトン メンバー関数の実装が定義されています。  メッセージ、イベント、およびディスパッチ マップも定義されています。|  
|*Projname*dlg.cpp、*Projname*dlg.h|ダイアログ ベースのアプリケーションを選択した場合に作成されるファイル。  これらのファイルは、ダイアログ クラスである `CProjnameDlg` を派生して実装します。また、ダイアログを初期化し、ダイアログ データ エクスチェンジ \(DDX: Dialog Data Exchange\) を実行するスケルトン メンバー関数も含まれます。  \[バージョン情報\] ダイアログ クラスも、*Projname*.cpp ではなく、これらのファイルに記述されています。|  
|Dlgproxy.cpp、Dlgproxy.h|ダイアログ ベースのプログラムでは、主要なダイアログに対するプロジェクトのオートメーション プロキシ クラスの実装ファイルおよびヘッダー ファイル。  オートメーションのサポートを選択した場合にだけ使用されます。|  
|*Projname*doc.cpp、*Projname*doc.h|ドキュメント クラスである `CProjnameDoc` を派生して実装するファイル。このファイルには、ドキュメントの初期化およびシリアル化 \(保存と読み込み\) を行い、デバッグ時の診断プログラムを実装するスケルトン メンバー関数が含まれます。|  
|*Projname*set.h、*Projname*set.cpp|データベースをサポートし、レコードセット クラスを含むプログラムを作成する場合に生成されるファイル。|  
|*Projname*view.cpp、*Projname*view.h|ビュー クラスである `CProjnameView` を派生して実装するファイル。ビュー クラスは、ドキュメント データの表示や印刷に使用されます。  `CProjnameView` クラスは、以下のいずれかの MFC クラスから派生します。<br /><br /> -   [CEditView](../Topic/CEditView%20Class.md)<br />-   [CFormView](../mfc/reference/cformview-class.md)<br />-   [CRecordView](../mfc/reference/crecordview-class.md)<br />-   [COleDBRecordView](../mfc/reference/coledbrecordview-class.md)<br />-   [CTreeView](../mfc/reference/ctreeview-class.md)<br />-   [CListView](../mfc/reference/clistview-class.md)<br />-   [CRichEditView](../mfc/reference/cricheditview-class.md)<br />-   [CScrollView](../mfc/reference/cscrollview-class.md)<br />-   [CView](../Topic/CView%20Class.md)<br />-   [CHTMLView](../mfc/reference/chtmlview-class.md)<br />-   [CHTMLEditView](../mfc/reference/chtmleditview-class.md)<br /><br /> プロジェクトのビュー クラスには、ビューの描画やデバッグ時の診断プログラムを実装するスケルトン メンバー関数があります。  印刷のサポートを有効にすると、印刷、印刷設定、印刷プレビューの各コマンド メッセージに対するメッセージ マップ エントリが追加されます。  これらのエントリは、基本ビュー クラスの対応するメンバー関数を呼び出します。|  
|*Projname*PropPage.h、*Projname*PropPage.cpp|`CProjnamePropPage` クラスを宣言して実装するファイル。  `CProjnamePropPage` は、`COlePropertyPage` クラスの派生クラスです。このクラスには、データ交換と正当性チェックを実装するためのスケルトン メンバー関数 `DoDataExchange` があります。|  
|IPframe.cpp、IPframe.h|アプリケーション ウィザードの \[複合ドキュメント サポート\] ページで \[ミニ サーバー\] か \[フル サーバー\] を選択した場合に作成されるファイル。  これらのファイルは、埋め込み先フレーム ウィンドウ クラスである **CInPlaceFrame** を派生して実装します。このクラスは、サーバーを埋め込み先でアクティブにするときにコンテナー プログラムで使用されます。|  
|Mainfrm.cpp、Mainfrm.h|[CFrameWnd](../mfc/reference/cframewnd-class.md) \(SDI アプリケーションの場合\) または [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) \(MDI アプリケーションの場合\) から **CMainFrame** クラスを派生するファイル。  アプリケーション ウィザードの \[アプリケーション オプション\] ページ \(手順 4\/6\) で該当するオプションを選択した場合、**CMainFrame** クラスは、ツール バー ボタンとステータス バーを生成します。  **CMainFrame** の使用方法については、「[アプリケーション ウィザードで作成されるフレーム ウィンドウ クラス](../mfc/frame-window-classes-created-by-the-application-wizard.md)」を参照してください。|  
|Childfrm.cpp、Childfrm.h|[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) から **CChildFrame** クラスを派生するファイル。  **CChildFrame** クラスは、MDI ドキュメント フレーム ウィンドウで使用します。  これらのファイルは、MDI オプションを選択すると必ず作成されます。|  
  
## 参照  
 [Visual C\+\+ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)   
 [ATL プログラムまたはコントロールのソース ファイルとヘッダー ファイル](../ide/atl-program-or-control-source-and-header-files.md)   
 [CLR プロジェクト](../ide/files-created-for-clr-projects.md)