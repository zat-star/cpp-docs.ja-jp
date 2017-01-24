---
title: "CWinApp クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinApp"
  - "hInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アプリケーション オブジェクト [C++]"
  - "CWinApp クラス"
  - "HINSTANCE"
  - "メイン オブジェクト"
ms.assetid: e426a3cd-0d15-40d6-bd55-beaa5feb2343
caps.latest.revision: 27
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWinApp クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows のアプリケーション オブジェクトを派生させるための基本クラスです。  
  
## 構文  
  
```  
class CWinApp : public CWinThread  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CWinApp::CWinApp](../Topic/CWinApp::CWinApp.md)|`CWinApp` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CWinApp::AddDocTemplate](../Topic/CWinApp::AddDocTemplate.md)|アプリケーションで利用できるドキュメント テンプレートのリストにドキュメント テンプレートを追加します。|  
|[CWinApp::AddToRecentFileList](../Topic/CWinApp::AddToRecentFileList.md)|MRU \(most recently used\) ファイル リストにファイル名を追加します。|  
|[CWinApp::ApplicationRecoveryCallback](../Topic/CWinApp::ApplicationRecoveryCallback.md)|アプリケーションが予期せず終了したときに、フレームワークによって呼び出されます。|  
|[CWinApp::CloseAllDocuments](../Topic/CWinApp::CloseAllDocuments.md)|開いているドキュメントをすべて閉じます。|  
|[CWinApp::CreatePrinterDC](../Topic/CWinApp::CreatePrinterDC.md)|プリンター デバイス コンテキストを作成します。|  
|[CWinApp::DelRegTree](../Topic/CWinApp::DelRegTree.md)|指定されたキーと、そのすべてのサブキーを削除します。|  
|[CWinApp::DoMessageBox](../Topic/CWinApp::DoMessageBox.md)|アプリケーション用に [AfxMessageBox](../Topic/AfxMessageBox.md) を実装します。|  
|[CWinApp::DoWaitCursor](../Topic/CWinApp::DoWaitCursor.md)|待機カーソルをオン、オフします。|  
|[CWinApp::EnableD2DSupport](../Topic/CWinApp::EnableD2DSupport.md)|アプリケーションの `D2D` のサポートを有効にします。  このメソッドは、メイン ウィンドウが初期化される前に呼び出します。|  
|[CWinApp::EnableHtmlHelp](../Topic/CWinApp::EnableHtmlHelp.md)|アプリケーションに、WinHelp ではなく、HTMLHelp を実装します。|  
|[CWinApp::EnableTaskbarInteraction](../Topic/CWinApp::EnableTaskbarInteraction.md)|タスク バー インタラクションを有効にします。|  
|[CWinApp::ExitInstance](../Topic/CWinApp::ExitInstance.md)|アプリケーション終了時の後処理のためにオーバーライドします。|  
|[CWinApp::GetApplicationRecoveryParameter](../Topic/CWinApp::GetApplicationRecoveryParameter.md)|アプリケーション復元メソッドの入力パラメーターを取得します。|  
|[CWinApp::GetApplicationRecoveryPingInterval](../Topic/CWinApp::GetApplicationRecoveryPingInterval.md)|回復コールバック関数が応答するまで再起動マネージャーが待機する時間を返します。|  
|[CWinApp::GetApplicationRestartFlags](../Topic/CWinApp::GetApplicationRestartFlags.md)|再起動マネージャーで使用されるフラグを返します。|  
|[CWinApp::GetAppRegistryKey](../Topic/CWinApp::GetAppRegistryKey.md)|HKEY\_CURRENT\_USER\\\<ソフトウェア名\>\\RegistryKey\\ProfileName のキーを返します。|  
|[CWinApp::GetDataRecoveryHandler](../Topic/CWinApp::GetDataRecoveryHandler.md)|アプリケーションのこのインスタンスに対するデータ復元ハンドラーを取得します。|  
|[CWinApp::GetFirstDocTemplatePosition](../Topic/CWinApp::GetFirstDocTemplatePosition.md)|最初のドキュメント テンプレートの位置を取得します。|  
|[CWinApp::GetHelpMode](../Topic/CWinApp::GetHelpMode.md)|アプリケーションで使用するヘルプのタイプを取得します。|  
|[CWinApp::GetNextDocTemplate](../Topic/CWinApp::GetNextDocTemplate.md)|ドキュメント テンプレートの位置を取得します。  再帰的に使用できます。|  
|[CWinApp::GetPrinterDeviceDefaults](../Topic/CWinApp::GetPrinterDeviceDefaults.md)|プリンター デバイスの既定の設定を取得します。|  
|[CWinApp::GetProfileBinary](../Topic/CWinApp::GetProfileBinary.md)|アプリケーションの .INI ファイルのエントリからバイナリ データを取得します。|  
|[CWinApp::GetProfileInt](../Topic/CWinApp::GetProfileInt.md)|アプリケーションの .INI ファイルのエントリから整数を取得します。|  
|[CWinApp::GetProfileString](../Topic/CWinApp::GetProfileString.md)|アプリケーションの .INI ファイルのエントリから文字列を取得します。|  
|[CWinApp::GetSectionKey](../Topic/CWinApp::GetSectionKey.md)|HKEY\_CURRENT\_USER\\\<ソフトウェア名\>\\RegistryKey\\AppName\\lpszSection のキーを返します。|  
|[CWinApp::HideApplication](../Topic/CWinApp::HideApplication.md)|すべてのドキュメントを閉じる前に、アプリケーションを非表示にします。|  
|[CWinApp::HtmlHelp](../Topic/CWinApp::HtmlHelp.md)|Windows の `HTMLHelp` 関数を呼び出します。|  
|[CWinApp::InitInstance](../Topic/CWinApp::InitInstance.md)|ウィンドウ オブジェクトの作成のような、Windows インスタンスの初期化を実行するためにオーバーライドします。|  
|[CWinApp::IsTaskbarInteractionEnabled](../Topic/CWinApp::IsTaskbarInteractionEnabled.md)|Windows 7 タスク バー インタラクションが有効であるかどうかを示します。|  
|[CWinApp::LoadCursor](../Topic/CWinApp::LoadCursor.md)|カーソル リソースを読み込みます。|  
|[CWinApp::LoadIcon](../Topic/CWinApp::LoadIcon.md)|アイコン リソースを読み込みます。|  
|[CWinApp::LoadOEMCursor](../Topic/CWinApp::LoadOEMCursor.md)|WINDOWS.H で定義されている **OCR\_** 定数で指定した Windows の OEM 組み込みカーソルを読み込みます。|  
|[CWinApp::LoadOEMIcon](../Topic/CWinApp::LoadOEMIcon.md)|WINDOWS.H で定義されている **OIC\_** 定数で指定した Windows の OEM 組み込みアイコンを読み込みます。|  
|[CWinApp::LoadStandardCursor](../Topic/CWinApp::LoadStandardCursor.md)|WINDOWS.H で定義されている **IDC\_** 定数で指定した Windows の組み込みカーソルを読み込みます。|  
|[CWinApp::LoadStandardIcon](../Topic/CWinApp::LoadStandardIcon.md)|WINDOWS.H で定義されている **IDI\_** 定数で指定した Windows の組み込みアイコンを読み込みます。|  
|[CWinApp::OnDDECommand](../Topic/CWinApp::OnDDECommand.md)|DDE \(dynamic data exchange\) 実行コマンドに対する応答としてフレームワークが呼び出します。|  
|[CWinApp::OnIdle](../Topic/CWinApp::OnIdle.md)|アプリケーション固有の入力待ち処理のためにオーバーライドします。|  
|[CWinApp::OpenDocumentFile](../Topic/CWinApp::OpenDocumentFile.md)|ファイルからドキュメントを開くために、フレームワークが呼び出します。|  
|[CWinApp::ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md)|コマンド ライン中のパラメーターとフラグをそれぞれ解析します。|  
|[CWinApp::PreTranslateMessage](../Topic/CWinApp::PreTranslateMessage.md)|Windows 関数の [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) や [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) にディスパッチする前にメッセージにフィルターをかけます。|  
|[CWinApp::ProcessMessageFilter](../Topic/CWinApp::ProcessMessageFilter.md)|アプリケーションに届く前に、特定のメッセージを受け取ります。|  
|[CWinApp::ProcessShellCommand](../Topic/CWinApp::ProcessShellCommand.md)|コマンド ライン引数とフラグを処理します。|  
|[CWinApp::ProcessWndProcException](../Topic/CWinApp::ProcessWndProcException.md)|アプリケーションのメッセージ ハンドラーやコマンド ハンドラーがスローしたすべての未処理の例外を受け取ります。|  
|[CWinApp::Register](../Topic/CWinApp::Register.md)|カスタマイズした登録を実行します。|  
|[CWinApp::RegisterWithRestartManager](../Topic/CWinApp::RegisterWithRestartManager.md)|アプリケーションを再起動マネージャーに登録します。|  
|[CWinApp::ReopenPreviousFilesAtRestart](../Topic/CWinApp::ReopenPreviousFilesAtRestart.md)|アプリケーションが予期せず終了したときに開かれていたファイルが再起動マネージャーによって再度開かれるかどうかを示します。|  
|[CWinApp::RestartInstance](../Topic/CWinApp::RestartInstance.md)|再起動マネージャーにより開始される、アプリケーションの再起動を処理します。|  
|[CWinApp::RestoreAutosavedFilesAtRestart](../Topic/CWinApp::RestoreAutosavedFilesAtRestart.md)|アプリケーションの再起動時に、自動保存されたファイルが再起動マネージャーによって復元されるかどうかを示します。|  
|[CWinApp::Run](../Topic/CWinApp::Run.md)|既定のメッセージ ループを実行します。  メッセージ ループをカスタマイズするためにオーバーライドします。|  
|[CWinApp::RunAutomated](../Topic/CWinApp::RunAutomated.md)|**\/Automation** オプションに対してアプリケーションのコマンド ラインをテストします。  互換性のために残されています。  代わりに、[ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md) を呼び出した後で、[CCommandLineInfo::m\_bRunAutomated](../Topic/CCommandLineInfo::m_bRunAutomated.md) の値を使用してください。|  
|[CWinApp::RunEmbedded](../Topic/CWinApp::RunEmbedded.md)|**\/Embedding** オプションに対してアプリケーションのコマンド ラインをテストします。  互換性のために残されています。  代わりに、[ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md) を呼び出した後で、[CCommandLineInfo::m\_bRunEmbedded](../Topic/CCommandLineInfo::m_bRunEmbedded.md) の値を使用してください。|  
|[CWinApp::SaveAllModified](../Topic/CWinApp::SaveAllModified.md)|変更されているすべてのドキュメントを保存するかどうかをユーザーに問い合わせます。|  
|[CWinApp::SelectPrinter](../Topic/CWinApp::SelectPrinter.md)|ユーザーが印刷ダイアログ ボックスを使って、以前に指定したプリンターを選択します。|  
|[CWinApp::SetHelpMode](../Topic/CWinApp::SetHelpMode.md)|アプリケーションで使用するヘルプのタイプを設定および初期化します。|  
|[CWinApp::SupportsApplicationRecovery](../Topic/CWinApp::SupportsApplicationRecovery.md)|予期せず終了したアプリケーションが再起動マネージャーによって回復されるかどうかを判断します。|  
|[CWinApp::SupportsAutosaveAtInterval](../Topic/CWinApp::SupportsAutosaveAtInterval.md)|開いているドキュメントが再起動マネージャーによって定期的に自動保存されるかどうかを示します。|  
|[CWinApp::SupportsAutosaveAtRestart](../Topic/CWinApp::SupportsAutosaveAtRestart.md)|アプリケーションの再起動時に、開いているドキュメントが再起動マネージャーによって自動保存されるかどうかを示します。|  
|[CWinApp::SupportsRestartManager](../Topic/CWinApp::SupportsRestartManager.md)|アプリケーションで再起動マネージャーがサポートされているかどうかを調べます。|  
|[CWinApp::Unregister](../Topic/CWinApp::Unregister.md)|`CWinApp` オブジェクトによって登録されているすべての登録を解除します。|  
|[CWinApp::WinHelp](../Topic/CWinApp::WinHelp.md)|Windows の `WinHelp` 関数を呼び出します。|  
|[CWinApp::WriteProfileBinary](../Topic/CWinApp::WriteProfileBinary.md)|アプリケーションの .INI ファイルのエントリにバイナリ データを書き込みます。|  
|[CWinApp::WriteProfileInt](../Topic/CWinApp::WriteProfileInt.md)|アプリケーションの .INI ファイルのエントリに整数を書き込みます。|  
|[CWinApp::WriteProfileString](../Topic/CWinApp::WriteProfileString.md)|アプリケーションの .INI ファイルのエントリに文字列を書き込みます。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CWinApp::EnableShellOpen](../Topic/CWinApp::EnableShellOpen.md)|Windows のファイル マネージャーからデータ ファイルを開けられるようにします。|  
|[CWinApp::LoadStdProfileSettings](../Topic/CWinApp::LoadStdProfileSettings.md)|標準の .INI ファイルの設定を読み込んで、MRU ファイル リスト機能を有効にします。|  
|[CWinApp::OnContextHelp](../Topic/CWinApp::OnContextHelp.md)|アプリケーション内で Shift \+ F1 ヘルプを処理します。|  
|[CWinApp::OnFileNew](../Topic/CWinApp::OnFileNew.md)|`ID_FILE_NEW` コマンドを実装します。|  
|[CWinApp::OnFileOpen](../Topic/CWinApp::OnFileOpen.md)|`ID_FILE_OPEN` コマンドを実装します。|  
|[CWinApp::OnFilePrintSetup](../Topic/CWinApp::OnFilePrintSetup.md)|`ID_FILE_PRINT_SETUP` コマンドを実装します。|  
|[CWinApp::OnHelp](../Topic/CWinApp::OnHelp.md)|アプリケーション内で F1 ヘルプを \(現在のコンテキストを使って\) 処理します。|  
|[CWinApp::OnHelpFinder](../Topic/CWinApp::OnHelpFinder.md)|`ID_HELP_FINDER` コマンドおよび `ID_DEFAULT_HELP` コマンドを処理します。|  
|[CWinApp::OnHelpIndex](../Topic/CWinApp::OnHelpIndex.md)|`ID_HELP_INDEX` コマンドを処理し、既定のヘルプ トピックを用意します。|  
|[CWinApp::OnHelpUsing](../Topic/CWinApp::OnHelpUsing.md)|`ID_HELP_USING` コマンドを処理します。|  
|[CWinApp::RegisterShellFileTypes](../Topic/CWinApp::RegisterShellFileTypes.md)|Windows のファイル マネージャーにすべてのアプリケーションのドキュメントの種類を登録します。|  
|[CWinApp::SetAppID](../Topic/CWinApp::SetAppID.md)|アプリケーションのユーザー モデル ID を明示的に設定します。  何らかのユーザー インターフェイスをユーザーに表示する前には、このメソッドを呼び出す必要があります \(最も適切な場所はアプリケーション コンストラクターです\)。|  
|[CWinApp::SetRegistryKey](../Topic/CWinApp::SetRegistryKey.md)|アプリケーションの設定を .INI ファイルの代わりにレジストリに格納します。|  
|[CWinApp::UnregisterShellFileTypes](../Topic/CWinApp::UnregisterShellFileTypes.md)|Windows のファイル マネージャーでアプリケーションのすべてのドキュメントの種類を登録解除します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CWinApp::m\_bHelpMode](../Topic/CWinApp::m_bHelpMode.md)|ヘルプ コンテキスト モード \(通常 Shift \+ F1 キーで起動\) かどうかを示します。|  
|[CWinApp::m\_eHelpType](../Topic/CWinApp::m_eHelpType.md)|アプリケーションで使用するヘルプのタイプを指定します。|  
|[CWinApp::m\_hInstance](../Topic/CWinApp::m_hInstance.md)|アプリケーションの現在のインスタンスを識別します。|  
|[CWinApp::m\_lpCmdLine](../Topic/CWinApp::m_lpCmdLine.md)|アプリケーションのコマンド ラインを指定する NULL で終わる文字列へのポインターです。|  
|[CWinApp::m\_nCmdShow](../Topic/CWinApp::m_nCmdShow.md)|初期状態でウィンドウをどう表示するかを指定します。|  
|[CWinApp::m\_pActiveWnd](../Topic/CWinApp::m_pActiveWnd.md)|OLE サーバーが埋め込み先編集が有効な場合のコンテナー アプリケーションのメイン ウィンドウへのポインターです。|  
|[CWinApp::m\_pszAppID](../Topic/CWinApp::m_pszAppID.md)|アプリケーションのユーザー モデル ID です。|  
|[CWinApp::m\_pszAppName](../Topic/CWinApp::m_pszAppName.md)|アプリケーション名を示します。|  
|[CWinApp::m\_pszExeName](../Topic/CWinApp::m_pszExeName.md)|アプリケーションのモジュール名です。|  
|[CWinApp::m\_pszHelpFilePath](../Topic/CWinApp::m_pszHelpFilePath.md)|アプリケーションのヘルプ ファイルのパスです。|  
|[CWinApp::m\_pszProfileName](../Topic/CWinApp::m_pszProfileName.md)|アプリケーションの .INI ファイル名です。|  
|[CWinApp::m\_pszRegistryKey](../Topic/CWinApp::m_pszRegistryKey.md)|アプリケーションのプロファイル設定を格納するためのフル レジストリ キーの特定に使います。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CWinApp::m\_dwRestartManagerSupportFlags](../Topic/CWinApp::m_dwRestartManagerSupportFlags.md)|再起動マネージャーがどのように動作するかを示すフラグです。|  
|[CWinApp::m\_nAutosaveInterval](../Topic/CWinApp::m_nAutosaveInterval.md)|自動保存の間隔 \(ミリ秒単位\) です。|  
|[CWinApp::m\_pDataRecoveryHandler](../Topic/CWinApp::m_pDataRecoveryHandler.md)|アプリケーションのデータ復元ハンドラーへのポインターです。|  
  
## 解説  
 アプリケーション オブジェクトはアプリケーション \(および、各インスタンス\) の初期化や、アプリケーションの実行のためのメンバー関数を提供します。  
  
 Microsoft Foundation Class を使った各アプリケーションは `CWinApp` から派生させたオブジェクトを 1 つだけ持つことができます。  このオブジェクトはほかの C\+\+ のグローバル オブジェクトが構築されるときに構築され、Windows によって `WinMain` 関数が呼び出されたときには利用できるように準備されます。`WinMain` 関数は Microsoft Foundation Class ライブラリが用意します。  `CWinApp` 派生クラスのオブジェクトはグローバル レベルで宣言します。  
  
 `CWinApp` からアプリケーション クラスを派生したとき、アプリケーションのメイン ウィンドウ オブジェクトを作成するために [InitInstance](../Topic/CWinApp::InitInstance.md) メンバー関数をオーバーライドします。  
  
 `CWinApp` のメンバー関数に加えて、Microsoft Foundation Class ライブラリには、以下に示すような `CWinApp` オブジェクトやほかのグローバル情報にアクセスするためのグローバル関数が用意されています。  
  
-   [AfxGetApp](../Topic/AfxGetApp.md) は `CWinApp` のポインターを取得します。  
  
-   [AfxGetInstanceHandle](../Topic/AfxGetInstanceHandle.md) は、現在のアプリケーションのインスタンスへのハンドルを取得します。  
  
-   [AfxGetResourceHandle](../Topic/AfxGetResourceHandle.md) は、アプリケーションのリソースへのハンドルを取得します。  
  
-   [AfxGetAppName](../Topic/AfxGetAppName.md) はアプリケーション名を含む文字列へのポインターを取得します。  `CWinApp` オブジェクトへのポインターがあるときにアプリケーション名を取得するには、代わりに `m_pszExeName` を使います。  
  
 `CWinApp` クラスの詳細および以下に関する概要については、「[CWinApp : アプリケーション クラス](../Topic/CWinApp:%20The%20Application%20Class.md)」を参照してください。  
  
-   アプリケーション ウィザードで記述した `CWinApp` からの派生コード  
  
-   アプリケーションの実行手順での `CWinApp` の役割  
  
-   `CWinApp` のメンバー関数の既定の実装  
  
-   `CWinApp` のキーであるオーバーライド可能な関数  
  
 **m\_hPrevInstance** データ メンバーはなくなりました。  `CWinApp` の前のインスタンスの検出については、[http:\/\/support.microsoft.com\/default.aspx?scid\=kb;ja\-jp;106385](http://support.microsoft.com/default.aspx?scid=kb;ja-jp;106385) のサポート技術情報「アプリケーションの前のインスタンスを特定する方法 \(KB106385\)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 `CWinApp`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [CWinThread クラス](../../mfc/reference/cwinthread-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [方法: 再起動マネージャーのサポートを追加する](../../mfc/how-to-add-restart-manager-support.md)