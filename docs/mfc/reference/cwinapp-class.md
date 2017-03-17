---
title: "CWinApp クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinApp
- AFXWIN/CWinApp
- AFXWIN/CWinApp::CWinApp
- AFXWIN/CWinApp::AddDocTemplate
- AFXWIN/CWinApp::AddToRecentFileList
- AFXWIN/CWinApp::ApplicationRecoveryCallback
- AFXWIN/CWinApp::CloseAllDocuments
- AFXWIN/CWinApp::CreatePrinterDC
- AFXWIN/CWinApp::DelRegTree
- AFXWIN/CWinApp::DoMessageBox
- AFXWIN/CWinApp::DoWaitCursor
- AFXWIN/CWinApp::EnableD2DSupport
- AFXWIN/CWinApp::EnableHtmlHelp
- AFXWIN/CWinApp::EnableTaskbarInteraction
- AFXWIN/CWinApp::ExitInstance
- AFXWIN/CWinApp::GetApplicationRecoveryParameter
- AFXWIN/CWinApp::GetApplicationRecoveryPingInterval
- AFXWIN/CWinApp::GetApplicationRestartFlags
- AFXWIN/CWinApp::GetAppRegistryKey
- AFXWIN/CWinApp::GetDataRecoveryHandler
- AFXWIN/CWinApp::GetFirstDocTemplatePosition
- AFXWIN/CWinApp::GetHelpMode
- AFXWIN/CWinApp::GetNextDocTemplate
- AFXWIN/CWinApp::GetPrinterDeviceDefaults
- AFXWIN/CWinApp::GetProfileBinary
- AFXWIN/CWinApp::GetProfileInt
- AFXWIN/CWinApp::GetProfileString
- AFXWIN/CWinApp::GetSectionKey
- AFXWIN/CWinApp::HideApplication
- AFXWIN/CWinApp::HtmlHelp
- AFXWIN/CWinApp::InitInstance
- AFXWIN/CWinApp::IsTaskbarInteractionEnabled
- AFXWIN/CWinApp::LoadCursor
- AFXWIN/CWinApp::LoadIcon
- AFXWIN/CWinApp::LoadOEMCursor
- AFXWIN/CWinApp::LoadOEMIcon
- AFXWIN/CWinApp::LoadStandardCursor
- AFXWIN/CWinApp::LoadStandardIcon
- AFXWIN/CWinApp::OnDDECommand
- AFXWIN/CWinApp::OnIdle
- AFXWIN/CWinApp::OpenDocumentFile
- AFXWIN/CWinApp::ParseCommandLine
- AFXWIN/CWinApp::PreTranslateMessage
- AFXWIN/CWinApp::ProcessMessageFilter
- AFXWIN/CWinApp::ProcessShellCommand
- AFXWIN/CWinApp::ProcessWndProcException
- AFXWIN/CWinApp::Register
- AFXWIN/CWinApp::RegisterWithRestartManager
- AFXWIN/CWinApp::ReopenPreviousFilesAtRestart
- AFXWIN/CWinApp::RestartInstance
- AFXWIN/CWinApp::RestoreAutosavedFilesAtRestart
- AFXWIN/CWinApp::Run
- AFXWIN/CWinApp::RunAutomated
- AFXWIN/CWinApp::RunEmbedded
- AFXWIN/CWinApp::SaveAllModified
- AFXWIN/CWinApp::SelectPrinter
- AFXWIN/CWinApp::SetHelpMode
- AFXWIN/CWinApp::SupportsApplicationRecovery
- AFXWIN/CWinApp::SupportsAutosaveAtInterval
- AFXWIN/CWinApp::SupportsAutosaveAtRestart
- AFXWIN/CWinApp::SupportsRestartManager
- AFXWIN/CWinApp::Unregister
- AFXWIN/CWinApp::WinHelp
- AFXWIN/CWinApp::WriteProfileBinary
- AFXWIN/CWinApp::WriteProfileInt
- AFXWIN/CWinApp::WriteProfileString
- AFXWIN/CWinApp::EnableShellOpen
- AFXWIN/CWinApp::LoadStdProfileSettings
- AFXWIN/CWinApp::OnContextHelp
- AFXWIN/CWinApp::OnFileNew
- AFXWIN/CWinApp::OnFileOpen
- AFXWIN/CWinApp::OnFilePrintSetup
- AFXWIN/CWinApp::OnHelp
- AFXWIN/CWinApp::OnHelpFinder
- AFXWIN/CWinApp::OnHelpIndex
- AFXWIN/CWinApp::OnHelpUsing
- AFXWIN/CWinApp::RegisterShellFileTypes
- AFXWIN/CWinApp::SetAppID
- AFXWIN/CWinApp::SetRegistryKey
- AFXWIN/CWinApp::UnregisterShellFileTypes
- AFXWIN/CWinApp::m_bHelpMode
- AFXWIN/CWinApp::m_eHelpType
- AFXWIN/CWinApp::m_hInstance
- AFXWIN/CWinApp::m_lpCmdLine
- AFXWIN/CWinApp::m_nCmdShow
- AFXWIN/CWinApp::m_pActiveWnd
- AFXWIN/CWinApp::m_pszAppID
- AFXWIN/CWinApp::m_pszAppName
- AFXWIN/CWinApp::m_pszExeName
- AFXWIN/CWinApp::m_pszHelpFilePath
- AFXWIN/CWinApp::m_pszProfileName
- AFXWIN/CWinApp::m_pszRegistryKey
- AFXWIN/CWinApp::m_dwRestartManagerSupportFlags
- AFXWIN/CWinApp::m_nAutosaveInterval
- AFXWIN/CWinApp::m_pDataRecoveryHandler
dev_langs:
- C++
helpviewer_keywords:
- CWinApp class
- application objects [C++]
- HINSTANCE
- main object
ms.assetid: e426a3cd-0d15-40d6-bd55-beaa5feb2343
caps.latest.revision: 27
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 292816c8f753a7b47b563a3fcd0fa336e08acd6a
ms.lasthandoff: 02/24/2017

---
# <a name="cwinapp-class"></a>CWinApp クラス
Windows のアプリケーション オブジェクトを派生させるための基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CWinApp : public CWinThread  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CWinApp::CWinApp](#cwinapp)|`CWinApp` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[とき](#adddoctemplate)|ドキュメント テンプレートをアプリケーションで利用できるドキュメント テンプレートのリストに追加します。|  
|[CWinApp::AddToRecentFileList](#addtorecentfilelist)|最近使用した MRU ファイル リストにファイル名を追加します。|  
|[CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)|アプリケーションが予期せず終了したときに、フレームワークによって呼び出されます。|  
|[CWinApp::CloseAllDocuments](#closealldocuments)|開いているドキュメントをすべて閉じます。|  
|[CWinApp::CreatePrinterDC](#createprinterdc)|プリンター デバイス コンテキストを作成します。|  
|[CWinApp::DelRegTree](#delregtree)|指定したキーとそのすべてのサブキーを削除します。|  
|[CWinApp::DoMessageBox](#domessagebox)|実装して[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)アプリケーションです。|  
|[CWinApp::DoWaitCursor](#dowaitcursor)|待機カーソルをオンおよびオフにします。|  
|[CWinApp::EnableD2DSupport](#enabled2dsupport)|アプリケーションで`D2D`をサポートします。 このメソッドは、メイン ウィンドウが初期化される前に呼び出します。|  
|[CWinApp::EnableHtmlHelp](#enablehtmlhelp)|WinHelp ではなく、アプリケーションの html ヘルプを実装します。|  
|[CWinApp::EnableTaskbarInteraction](#enabletaskbarinteraction)|タスク バーの相互作用を有効にします。|  
|[使う](#exitinstance)|アプリケーション終了時にクリーンアップするためにオーバーライドします。|  
|[CWinApp::GetApplicationRecoveryParameter](#getapplicationrecoveryparameter)|アプリケーションの復元メソッドの入力パラメーターを取得します。|  
|[CWinApp::GetApplicationRecoveryPingInterval](#getapplicationrecoverypinginterval)|再起動マネージャーが回復コールバック関数が返すまで待機する時間の長さを返します。|  
|[CWinApp::GetApplicationRestartFlags](#getapplicationrestartflags)|再起動マネージャーのフラグを返します。|  
|[CWinApp::GetAppRegistryKey](#getappregistrykey)|HKEY_CURRENT_USER のキーを返す\\「ソフトウェア」\RegistryKey\ProfileName します。|  
|[CWinApp::GetDataRecoveryHandler](#getdatarecoveryhandler)|アプリケーションのこのインスタンスのデータ回復のハンドラーを取得します。|  
|[CWinApp::GetFirstDocTemplatePosition](#getfirstdoctemplateposition)|最初のドキュメント テンプレートの位置を取得します。|  
|[CWinApp::GetHelpMode](#gethelpmode)|アプリケーションで使用するヘルプの種類を取得します。|  
|[CWinApp::GetNextDocTemplate](#getnextdoctemplate)|ドキュメント テンプレートの位置を取得します。 再帰的に使用できます。|  
|[CWinApp::GetPrinterDeviceDefaults](#getprinterdevicedefaults)|プリンター デバイスの既定値を取得します。|  
|[は](#getprofilebinary)|アプリケーションのエントリからバイナリ データを取得します。INI ファイルです。|  
|[は](#getprofileint)|アプリケーションのエントリから整数値を取得します。INI ファイルです。|  
|[CWinApp::GetProfileString](#getprofilestring)|アプリケーションのエントリから文字列を取得します。INI ファイルです。|  
|[CWinApp::GetSectionKey](#getsectionkey)|HKEY_CURRENT_USER のキーを返す\\「ソフトウェア」\RegistryKey\AppName\lpszSection します。|  
|[CWinApp::HideApplication](#hideapplication)|すべてのドキュメントを閉じる前にアプリケーションを非表示にします。|  
|[CWinApp::HtmlHelp](#htmlhelp)|呼び出し、 `HTMLHelp` Windows の機能です。|  
|[場合は](#initinstance)|ウィンドウ オブジェクトの作成など、Windows インスタンスを初期化するためにオーバーライドします。|  
|[CWinApp::IsTaskbarInteractionEnabled](#istaskbarinteractionenabled)|Windows 7 タスクバーの相互作用が有効になっているかどうかを指示します。|  
|[CWinApp::LoadCursor](#loadcursor)|カーソル リソースを読み込みます。|  
|[CWinApp::LoadIcon](#loadicon)|アイコン リソースを読み込みます。|  
|[CWinApp::LoadOEMCursor](#loadoemcursor)|Windows OEM の負荷の定義済みのカーソルを**OCR_** WINDOWS での定数を指定します。H.|  
|[CWinApp::LoadOEMIcon](#loadoemicon)|Windows OEM 定義済みのアイコンを読み込みますが、 **OIC_** WINDOWS での定数を指定します。H.|  
|[CWinApp::LoadStandardCursor](#loadstandardcursor)|読み込み、Windows にカーソルがあらかじめ定義されている、 **idc _** WINDOWS での定数を指定します。H.|  
|[CWinApp::LoadStandardIcon](#loadstandardicon)|Windows の定義済みのアイコンを読み込みますが、 **IDI_** WINDOWS での定数を指定します。H.|  
|[CWinApp::OnDDECommand](#onddecommand)|呼ばれる動的なデータへの応答として、フレームワークによってエクス (チェンジ DDE) がコマンドを実行します。|  
|[CWinApp::OnIdle](#onidle)|アプリケーション固有のアイドル状態時の処理を実行するためにオーバーライドします。|  
|[:Opendocumentfile](#opendocumentfile)|ファイルからドキュメントを開くために、フレームワークによって呼び出されます。|  
|[CWinApp::ParseCommandLine](#parsecommandline)|個々 のパラメーターとコマンド ラインでフラグを解析します。|  
|[Cwinapp::pretranslatemessage](#pretranslatemessage)|Windows の関数にディスパッチされる前にメッセージをフィルター処理[TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934)します。|  
|[CWinApp::ProcessMessageFilter](#processmessagefilter)|アプリケーションに到達する前に、特定のメッセージを受け取ります。|  
|[CWinApp::ProcessShellCommand](#processshellcommand)|コマンドライン引数とフラグを処理します。|  
|[CWinApp::ProcessWndProcException](#processwndprocexception)|アプリケーションのメッセージとコマンド ハンドラーによってスローされたすべてのハンドルされない例外を受け取ります。|  
|[CWinApp::Register](#register)|カスタマイズした登録を実行します。|  
|[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)|再起動マネージャーとのアプリケーションを登録します。|  
|[CWinApp::ReopenPreviousFilesAtRestart](#reopenpreviousfilesatrestart)|再起動マネージャーが、アプリケーションが予期せず終了したときに開いていたファイルを開くかどうかを決定します。|  
|[CWinApp::RestartInstance](#restartinstance)|再起動マネージャーによって開始されたアプリケーションの再起動を処理します。|  
|[CWinApp::RestoreAutosavedFilesAtRestart](#restoreautosavedfilesatrestart)|再起動マネージャーが、アプリケーションを再起動する際に、自動保存されたファイルを復元するかどうかを決定します。|  
|[:Run](#run)|既定のメッセージ ループを実行します。 メッセージ ループをカスタマイズするためにオーバーライドします。|  
|[CWinApp::RunAutomated](#runautomated)|アプリケーションのコマンドラインのテスト、 **/Automation**オプション。 互換性のために残されています。 代わりに、値を使用して[CCommandLineInfo::m_bRunAutomated](../../mfc/reference/ccommandlineinfo-class.md#m_brunautomated)呼び出した後[ParseCommandLine](#parsecommandline)します。|  
|[CWinApp::RunEmbedded](#runembedded)|アプリケーションのコマンドラインのテスト、 **埋め込み/**オプション。 互換性のために残されています。 代わりに、値を使用して[CCommandLineInfo::m_bRunEmbedded](../../mfc/reference/ccommandlineinfo-class.md#m_brunembedded)呼び出した後[ParseCommandLine](#parsecommandline)します。|  
|[CWinApp::SaveAllModified](#saveallmodified)|すべての修正済みのドキュメントを保存するユーザーに求めます。|  
|[通知](#selectprinter)|印刷ダイアログ ボックスでユーザーが以前に示されているプリンターを選択します。|  
|[CWinApp::SetHelpMode](#sethelpmode)|設定して、アプリケーションで使用するヘルプの種類を初期化します。|  
|[CWinApp::SupportsApplicationRecovery](#supportsapplicationrecovery)|再起動マネージャーが予期せず終了したアプリケーションを回復するかどうかを決定します。|  
|[CWinApp::SupportsAutosaveAtInterval](#supportsautosaveatinterval)|再起動マネージャーによって自動保存が一定の間隔でドキュメントを開くかどうかを決定します。|  
|[CWinApp::SupportsAutosaveAtRestart](#supportsautosaveatrestart)|指定するかどうか再起動マネージャーによって自動保存、アプリケーションの再起動時に、開いているドキュメントです。|  
|[CWinApp::SupportsRestartManager](#supportsrestartmanager)|アプリケーションが再起動マネージャーをサポートしているかどうかを決定します。|  
|[CWinApp::Unregister](#unregister)|すべての登録をして登録する登録解除、`CWinApp`オブジェクトです。|  
|[Cwinapp::winhelp](#winhelp)|呼び出し、 `WinHelp` Windows の機能です。|  
|[CWinApp::WriteProfileBinary](#writeprofilebinary)|アプリケーションのエントリには、バイナリ データを書き込みます。INI ファイルです。|  
|[Cwinapp::writeprofileint](#writeprofileint)|アプリケーションのエントリに整数を書き込みます。INI ファイルです。|  
|[CWinApp::WriteProfileString](#writeprofilestring)|アプリケーションのエントリには、文字列を書き込みます。INI ファイルです。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWinApp::EnableShellOpen](#enableshellopen)|Windows ファイル マネージャーからのデータ ファイルを開くユーザーができます。|  
|[既定](#loadstdprofilesettings)|標準の.INI ファイルの設定を有効、MRU ファイル リスト機能をします。|  
|[CWinApp::OnContextHelp](#oncontexthelp)|アプリケーション内で shift キーを押しながら F1 ヘルプを処理します。|  
|[CWinApp::OnFileNew](#onfilenew)|実装して、`ID_FILE_NEW`コマンドです。|  
|[CWinApp::OnFileOpen](#onfileopen)|実装して、`ID_FILE_OPEN`コマンドです。|  
|[CWinApp::OnFilePrintSetup](#onfileprintsetup)|実装して、`ID_FILE_PRINT_SETUP`コマンドです。|  
|[:Onhelp](#onhelp)|アプリケーション内で F1 ヘルプを (現在のコンテキストを使って) 処理します。|  
|[CWinApp::OnHelpFinder](#onhelpfinder)|`ID_HELP_FINDER` コマンドおよび `ID_DEFAULT_HELP` コマンドを処理します。|  
|[CWinApp::OnHelpIndex](#onhelpindex)|`ID_HELP_INDEX` コマンドを処理し、既定のヘルプ トピックを用意します。|  
|[CWinApp::OnHelpUsing](#onhelpusing)|`ID_HELP_USING` コマンドを処理します。|  
|[登録](#registershellfiletypes)|Windows ファイル マネージャーで、アプリケーションのすべてのドキュメントの種類を登録します。|  
|[CWinApp::SetAppID](#setappid)|アプリケーションのアプリケーションのユーザーのモデル ID を明示的に設定します。 すべてのユーザー インターフェイスを (最適な場所は、アプリケーションのコンス トラクターは) ユーザーに表示する前に、このメソッドを呼び出す必要があります。|  
|[書き込むに](#setregistrykey)|アプリケーション設定の代わりにレジストリに格納されます。INI ファイルです。|  
|[CWinApp::UnregisterShellFileTypes](#unregistershellfiletypes)|ドキュメントの種類のアプリケーションのすべての Windows ファイル マネージャーでの登録を解除します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CWinApp::m_bHelpMode](#m_bhelpmode)|ユーザーがヘルプ コンテキストのモード (通常は shift キーを押しながら f1 キーで起動される) かどうかを示します。|  
|[CWinApp::m_eHelpType](#m_ehelptype)|アプリケーションで使用するヘルプの種類を指定します。|  
|[CWinApp::m_hInstance](#m_hinstance)|アプリケーションの現在のインスタンスを識別します。|  
|[CWinApp::m_lpCmdLine](#m_lpcmdline)|アプリケーションのコマンドラインを指定する null で終わる文字列へのポインター。|  
|[CWinApp::m_nCmdShow](#m_ncmdshow)|ウィンドウの最初に表示する方法を指定します。|  
|[先](#m_pactivewnd)|OLE サーバーがアクティブである場合は、コンテナー アプリケーションのメイン ウィンドウへのポインター。|  
|[CWinApp::m_pszAppID](#m_pszappid)|アプリケーションのユーザーのモデル id です。|  
|[CWinApp::m_pszAppName](#m_pszappname)|アプリケーション名を示します。|  
|[CWinApp::m_pszExeName](#m_pszexename)|アプリケーションのモジュールの名前。|  
|[CWinApp::m_pszHelpFilePath](#m_pszhelpfilepath)|アプリケーションのヘルプ ファイルへのパス。|  
|[CWinApp::m_pszProfileName](#m_pszprofilename)|アプリケーションの.INI ファイル名です。|  
|[CWinApp::m_pszRegistryKey](#m_pszregistrykey)|アプリケーションのプロファイル設定を格納するためのフル レジストリ キーを判断するために使用します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CWinApp::m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags)|再起動マネージャーの動作を決定するフラグです。|  
|[CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)|自動保存の間隔をミリ秒単位で時間の長さ。|  
|[CWinApp::m_pDataRecoveryHandler](#m_pdatarecoveryhandler)|アプリケーションのデータ回復ハンドラーへのポインター。|  
  
## <a name="remarks"></a>コメント  
 アプリケーション オブジェクトは、アプリケーション (およびの各インスタンス) を初期化して、アプリケーションを実行するために、メンバー関数を提供します。  
  
 Microsoft Foundation classes を使用する各アプリケーションから派生した&1; つのオブジェクトを含めることができますのみ`CWinApp`します。 このオブジェクトは、その他の C++ のグローバル オブジェクトが構築されるときに作成し、Windows を呼び出すときに使用可能なは既に、`WinMain`関数で、Microsoft Foundation Class ライブラリによって提供されます。 派生宣言`CWinApp`グローバル レベルのオブジェクト。  
  
 アプリケーションのクラスを継承する場合`CWinApp`、オーバーライド、 [InitInstance](#initinstance)アプリケーションのメイン ウィンドウのオブジェクトを作成します。  
  
 加え、`CWinApp`メンバー関数にアクセスする次のグローバル関数を提供する、Microsoft Foundation Class ライブラリ、`CWinApp`オブジェクトおよびその他のグローバル情報。  
  
- [AfxGetApp](application-information-and-management.md#afxgetapp)へのポインターを取得、`CWinApp`オブジェクトです。  
  
- [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle)現在のアプリケーション インスタンスへのハンドルを取得します。  
  
- [AfxGetResourceHandle](application-information-and-management.md#afxgetresourcehandle)アプリケーションのリソースを識別するハンドルを取得します。  
  
- [AfxGetAppName](application-information-and-management.md#afxgetappname)アプリケーションの名前を含む文字列へのポインターを取得します。 代わりへのポインターがある場合、`CWinApp`オブジェクトを使用`m_pszExeName`アプリケーションの名前を取得します。  
  
 参照してください[CWinApp: アプリケーション クラス](../../mfc/cwinapp-the-application-class.md)の詳細について、 `CWinApp` class が、次の概要について説明します。  
  
- `CWinApp`-アプリケーション ウィザードによって作成されたコードを派生します。  
  
- `CWinApp`ロール、アプリケーションの実行順序にします。  
  
- `CWinApp`既定のメンバー関数の実装です。  
  
- `CWinApp`キーのオーバーライド可能な関数です。  
  
 **M_hPrevInstance**データ メンバーが存在しません。 以前のインスタンスを検出する方法について`CWinApp`にあるサポート技術情報の記事「方法を識別、前のインスタンスのアプリケーションへ」(KB106385) を参照してください[http://support.microsoft.com/default.aspxscid=kb;en-us;106385](http://support.microsoft.com/default.aspxscid=kb;en-us;106385)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 `CWinApp`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="adddoctemplate"></a>とき  
 ドキュメント テンプレートをアプリケーションが管理する利用可能なドキュメント テンプレートの一覧に追加するのには、このメンバー関数を呼び出します。  
  
```  
void AddDocTemplate(CDocTemplate* pTemplate);
```  
  
### <a name="parameters"></a>パラメーター  
 `pTemplate`  
 ポインター、`CDocTemplate`を追加します。  
  
### <a name="remarks"></a>コメント  
 呼び出す前に、すべてのドキュメントをアプリケーションにテンプレートを追加する必要があります[RegisterShellFileTypes](#registershellfiletypes)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&#35;](../../mfc/reference/codesnippet/cpp/cwinapp-class_1.cpp)]  
  
##  <a name="addtorecentfilelist"></a>CWinApp::AddToRecentFileList  
 追加するには、このメンバー関数を呼び出す`lpszPathName`MRU ファイル リストにします。  
  
```  
virtual void AddToRecentFileList(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszPathName`  
 ファイルのパス。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります、 [LoadStdProfileSettings](#loadstdprofilesettings)メンバー関数をこのメンバー関数を使用する前に、現在の MRU ファイル リストを読み込めません。  
  
 フレームワークは、ファイルを開くか、新しい名前でファイルを保存する名前を付けて保存 を実行することと、このメンバー関数を呼び出します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&#36;](../../mfc/reference/codesnippet/cpp/cwinapp-class_2.cpp)]  
  
##  <a name="applicationrecoverycallback"></a>CWinApp::ApplicationRecoveryCallback  
 アプリケーションが予期せず終了したときに、フレームワークによって呼び出されます。  
  
```  
virtual DWORD ApplicationRecoveryCallback(LPVOID lpvParam);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpvParam`  
 将来使用するために予約されています。  
  
### <a name="return-value"></a>戻り値  
 このメソッドが成功した場合は&0;以外の場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションでは、再起動マネージャーをサポートする場合、フレームワークは、アプリケーションが予期せず終了したときに、この関数を呼び出します。  
  
 既定の実装`ApplicationRecoveryCallback`を使用して、`CDataRecoveryHandler`を現在開いているドキュメントの一覧をレジストリに保存します。 このメソッドは、すべてのファイルを自動保存にしません。  
  
 動作をカスタマイズするには、派生では、この関数をオーバーライド[CWinApp クラス](../../mfc/reference/cwinapp-class.md)へのパラメーターとして、独自のアプリケーションの回復メソッドを渡すことも[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)します。  
  
##  <a name="closealldocuments"></a>CWinApp::CloseAllDocuments  
 このメンバー関数を呼び出して終了する前にすべての開いているドキュメントを閉じます。  
  
```  
void CloseAllDocuments(BOOL bEndSession);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEndSession`  
 Windows セッションを終了するかどうかを指定します。 **TRUE**終了以外の場合、セッションがされている場合は**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 呼び出す[HideApplication](#hideapplication)呼び出す前に`CloseAllDocuments`します。  
  
##  <a name="createprinterdc"></a>CWinApp::CreatePrinterDC  
 選択したプリンターのプリンター デバイス コンテキスト (DC) を作成するには、このメンバー関数を呼び出します。  
  
```  
BOOL CreatePrinterDC(CDC& dc);
```  
  
### <a name="parameters"></a>パラメーター  
 `dc`  
 プリンター デバイス コンテキストへの参照。  
  
### <a name="return-value"></a>戻り値  
 プリンター デバイス コンテキストを正常に作成する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `CreatePrinterDC`参照渡しするで、印刷に使用できるようにしているデバイス コンテキストを初期化します。  
  
 印刷が完了したときに、関数が成功した場合は、デバイス コンテキストを破棄する必要があります。 デストラクターを使用する、 [CDC](../../mfc/reference/cdc-class.md)オブジェクトを実行して、またはを呼び出して明示的に行うことができます[デバイス コンテキストの破棄](../../mfc/reference/cdc-class.md#deletedc)します。  
  
##  <a name="cwinapp"></a>CWinApp::CWinApp  
 構築、`CWinApp`オブジェクトを渡します`lpszAppName`をアプリケーション名として保存します。  
  
```  
CWinApp(LPCTSTR lpszAppName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszAppName`  
 Windows で使用されるアプリケーション名を表す null で終わる文字列。 この引数が指定されていないか、 **NULL**、`CWinApp`リソース文字列を使用して**AFX_IDS_APP_TITLE**または実行可能ファイルのファイル名。  
  
### <a name="remarks"></a>コメント  
 1 つのグローバル オブジェクトを構築する必要があります、 `CWinApp`-クラスを派生します。 1 つだけ持つことができます`CWinApp`アプリケーション内のオブジェクト。 コンス トラクターへのポインターを格納する、`CWinApp`オブジェクトように`WinMain`オブジェクトのメンバーを初期化し、アプリケーションを実行する関数を呼び出すことができます。  
  
##  <a name="delregtree"></a>CWinApp::DelRegTree  
 特定のレジストリ キーおよびそのすべてのサブキーを削除します。  
  
```  
LONG DelRegTree(
    HKEY hParentKey,  
    const CString& strKeyName);

 
LONG DelRegTree(
    HKEY hParentKey,
    const CString& strKeyName,
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *hParentKey*  
 レジストリ キーへのハンドルします。  
  
 *strKeyName*  
 削除するレジストリ キーの名前。  
  
 *pTM*  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は、error_success を返しますを返します。 関数が失敗した場合は、Winerror.h で定義されている&0; 以外のエラー コードは、戻り値。  
  
### <a name="remarks"></a>コメント  
 指定したキーとそのサブキーを削除するには、この関数を呼び出します。  
  
##  <a name="domessagebox"></a>CWinApp::DoMessageBox  
 グローバル関数でメッセージ ボックスを実装するには、このメンバー関数がフレームワーク[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)します。  
  
```  
virtual int DoMessageBox(
    LPCTSTR lpszPrompt,  
    UINT nType,  
    UINT nIDPrompt);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszPrompt*  
 メッセージ ボックスにテキストのアドレス。  
  
 `nType`  
 メッセージ ボックス[スタイル](../../mfc/reference/message-box-styles.md)します。  
  
 `nIDPrompt`  
 ヘルプ コンテキストの文字列のインデックスです。  
  
### <a name="return-value"></a>戻り値  
 同じ値を返す`AfxMessageBox`します。  
  
### <a name="remarks"></a>コメント  
 メッセージ ボックスを開くには、このメンバー関数を呼び出す必要はありません。使用して`AfxMessageBox`代わりにします。  
  
 アプリケーション全体の処理をカスタマイズするには、この関数をオーバーライド`AfxMessageBox`呼び出しです。  
  
##  <a name="dowaitcursor"></a>CWinApp::DoWaitCursor  
 実装するためにフレームワークによって呼び出されます[CWaitCursor](../../mfc/reference/cwaitcursor-class.md)、 [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)、 [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)、および[CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)します。  
  
```  
virtual void DoWaitCursor(int nCode);
```  
  
### <a name="parameters"></a>パラメーター  
 `nCode`  
 このパラメーターが 1 の場合は、待機カーソルが表示されます。 0 の場合、参照カウントをインクリメントせずに待機カーソルが復元されます。 -1 のとき、待機カーソルを終了します。  
  
### <a name="remarks"></a>コメント  
 既定では、砂時計カーソルを実装します。 `DoWaitCursor`参照カウントを保持します。 正の値と砂時計カーソルが表示されます。  
  
 呼び出すこと、`DoWaitCursor`を直接待機カーソルを変更または待機カーソルが表示されている間に追加の処理を行うには、このメンバー関数をオーバーライドする可能性があります。  
  
 使用する方法についてよりやさしくより効率的な待機カーソルを実装する、`CWaitCursor`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&37;](../../mfc/reference/codesnippet/cpp/cwinapp-class_3.cpp)]  
  
##  <a name="enabled2dsupport"></a>CWinApp::EnableD2DSupport  
 [!INCLUDE[dev10_sp1required](../../mfc/reference/includes/dev10_sp1required_md.md)]  
  
 アプリケーション D2D のサポートを有効にします。 このメソッドは、メイン ウィンドウが初期化される前に呼び出します。  
  
```  
BOOL EnableD2DSupport(
D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,  
DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```  
  
### <a name="parameters"></a>パラメーター  
 `d2dFactoryType`  
 D2D ファクトリとリソースのスレッド モデルが作成されます。  
  
 `writeFactoryType`  
 書き込みのファクトリ オブジェクトが共有か分離かどうかを指定する値  
  
### <a name="return-value"></a>戻り値  
 D2D サポートが有効な場合は false を指定すると、それ以外の場合は TRUE を返します  
  
##  <a name="enablehtmlhelp"></a>CWinApp::EnableHtmlHelp  
 コンス トラクター内からこのメンバー関数を呼び出して、 `CWinApp`-アプリケーションのヘルプの html ヘルプを使用するクラスを派生します。  
  
```  
void EnableHtmlHelp();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enableshellopen"></a>CWinApp::EnableShellOpen  
 通常、関数を呼び出す、`InitInstance`オーバーライドは、Windows ファイル マネージャー内からファイルをダブルクリックしたときに、データ ファイルを開くアプリケーションのユーザーを有効にします。  
  
```  
void EnableShellOpen();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す、`RegisterShellFileTypes`メンバーは、この関数を組み合わせて機能または提供します。ドキュメントの種類の手動登録のため、アプリケーションと共に REG ファイルです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&38;](../../mfc/reference/codesnippet/cpp/cwinapp-class_4.cpp)]  
  
##  <a name="enabletaskbarinteraction"></a>CWinApp::EnableTaskbarInteraction  
 タスク バーの相互作用を有効にします。  
  
```  
BOOL EnableTaskbarInteraction(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnable`  
 Windows 7 タスク バーとの対話を有効にするかどうかを指定します ( `TRUE`)、または無効になっています ( `FALSE`)。  
  
### <a name="return-value"></a>戻り値  
 返します。`TRUE`タスク バーの相互作用を有効または無効になっている場合。  
  
### <a name="remarks"></a>コメント  
 メイン ウィンドウの作成前に、このメソッドを呼び出す必要があります、それ以外の場合はアサートし、返します`FALSE`します。  
  
##  <a name="exitinstance"></a>使う  
 内から、フレームワークによって呼び出されます、**実行**メンバー関数をアプリケーションのこのインスタンスを終了します。  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションの終了コード。0 なし、エラーを示し、エラーを示す 0 より大きい値です。 この値はからの戻り値として使用`WinMain`します。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要はありません、このメンバー関数どこからでも、内部、**実行**メンバー関数。  
  
 この関数の既定の実装では、アプリケーションのフレームワーク オプションを書き込みます。INI ファイルです。 アプリケーション終了時にクリーンアップするには、この関数をオーバーライドします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&#39;](../../mfc/reference/codesnippet/cpp/cwinapp-class_5.cpp)]  
  
##  <a name="getapplicationrecoveryparameter"></a>CWinApp::GetApplicationRecoveryParameter  
 アプリケーションの復元メソッドの入力パラメーターを取得します。  
  
```  
virtual LPVOID GetApplicationRecoveryParameter();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションの回復方法の既定の入力パラメーターです。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の動作`NULL`します。  
  
 詳細については、次を参照してください。 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)します。  
  
##  <a name="getapplicationrecoverypinginterval"></a>CWinApp::GetApplicationRecoveryPingInterval  
 再起動マネージャーが回復コールバック関数が返すまで待機する時間の長さを返します。  
  
```  
virtual DWORD GetApplicationRecoveryPingInterval();
```  
  
### <a name="return-value"></a>戻り値  
 時間 (ミリ秒) の長さ。  
  
### <a name="remarks"></a>コメント  
 予期せず再起動マネージャーが終了に登録されているアプリケーション、アプリケーションの開いているドキュメントを保存しようとして回復コールバック関数を呼び出します。 既定の回復のコールバック関数は、 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)します。  
  
 フレームワークは回復のコールバック関数が返すまで待機する時間の長さは、ping の間隔です。 Ping の間隔をカスタマイズするには、オーバーライドする`CWinApp::GetApplicationRecoveryPingInterval`にカスタム値を提供することで、または`RegisterWithRestartManager`です。  
  
##  <a name="getapplicationrestartflags"></a>CWinApp::GetApplicationRestartFlags  
 再起動マネージャーのフラグを返します。  
  
```  
virtual DWORD GetApplicationRestartFlags();
```  
  
### <a name="return-value"></a>戻り値  
 再起動マネージャーのフラグ。 既定の実装では、0 を返します。  
  
### <a name="remarks"></a>コメント  
 再起動マネージャーのフラグは、既定の実装に影響を与えるありません。 将来の使用に対して用意されています。  
  
 再起動マネージャーを使用して、アプリケーションを登録するときに、フラグを設定する[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)します。  
  
 再起動マネージャーのフラグの値は次のとおりです。  
  
- `RESTART_NO_CRASH`  
  
- `RESTART_NO_HANG`  
  
- `RESTART_NO_PATCH`  
  
- `RESTART_NO_REBOOT`  
  
##  <a name="getappregistrykey"></a>CWinApp::GetAppRegistryKey  
 HKEY_CURRENT_USER のキーを返す\\「ソフトウェア」\RegistryKey\ProfileName します。  
  
```  
HKEY GetAppRegistryKey(CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pTM`  
 ポインター、`CAtlTransactionManager`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、アプリケーション キーそれ以外の場合`NULL`します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getdatarecoveryhandler"></a>CWinApp::GetDataRecoveryHandler  
 アプリケーションのこのインスタンスのデータ回復のハンドラーを取得します。  
  
```  
virtual CDataRecoveryHandler *GetDataRecoveryHandler();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションのこのインスタンスのデータ回復のハンドラーです。  
  
### <a name="remarks"></a>コメント  
 再起動マネージャーを使用する各アプリケーションは、1 つのインスタンスを持つ必要があります、 [CDataRecoveryHandler クラス](../../mfc/reference/cdatarecoveryhandler-class.md)します。 このクラスは、開いているドキュメントとファイルを自動保存の監視を担当します。 動作、`CDataRecoveryHandler`再起動マネージャーの構成によって異なります。 詳細については、次を参照してください。 [CDataRecoveryHandler クラス](../../mfc/reference/cdatarecoveryhandler-class.md)します。  
  
 このメソッドが戻る`NULL`オペレーティング システムでよりも前[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]します。 再起動マネージャーがオペレーティング システムでサポートされていませんよりも前[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]します。  
  
 アプリケーションが現在データ復元ハンドラーを持たない場合、このメソッドは&1; つを作成し、ポインターを返します。  
  
##  <a name="getfirstdoctemplateposition"></a>CWinApp::GetFirstDocTemplatePosition  
 アプリケーション内の最初のドキュメント テンプレートの位置を取得します。  
  
```  
POSITION GetFirstDocTemplatePosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**イテレーションまたはオブジェクト ポインターの取得のために使用する値**NULL**リストが空の場合。  
  
### <a name="remarks"></a>コメント  
 使用して、**位置**値への呼び出しで返される[GetNextDocTemplate](#getnextdoctemplate) 、最初に[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)オブジェクトです。  
  
##  <a name="gethelpmode"></a>CWinApp::GetHelpMode  
 アプリケーションで使用するヘルプの種類を取得します。  
  
```  
AFX_HELP_TYPE GetHelpMode();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションのヘルプ型です。 参照してください[CWinApp::m_eHelpType](#m_ehelptype)の詳細。  
  
##  <a name="getnextdoctemplate"></a>CWinApp::GetNextDocTemplate  
 識別されるドキュメント テンプレートを取得`pos`を設定し、`pos`に、**位置**値。  
  
```  
CDocTemplate* GetNextDocTemplate(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 参照、**位置**を以前の呼び出しによって返される値`GetNextDocTemplate`または[GetFirstDocTemplatePosition](#getfirstdoctemplateposition)します。 この呼び出しによって次の位置に値が更新されます。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 使用する`GetNextDocTemplate`への呼び出しでは、最初の位置を確立する場合は、順方向の反復ループで`GetFirstDocTemplatePosition`します。  
  
 確認する必要があります、**位置**値が無効です。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 取得したドキュメント テンプレートが最後の場合の新しい値`pos`に設定されている**NULL**します。  
  
##  <a name="getprinterdevicedefaults"></a>CWinApp::GetPrinterDeviceDefaults  
 印刷用のプリンター デバイス コンテキストを準備するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetPrinterDeviceDefaults(struct tagPDA* pPrintDlg);
```  
  
### <a name="parameters"></a>パラメーター  
 *pPrintDlg*  
 ポインター、 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843)構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 Windows の現在のプリンターの既定値を取得します。必要に応じて、または印刷のセットアップでユーザーが最後のプリンターの構成の設定を使用してとして INI ファイルです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&40;](../../mfc/reference/codesnippet/cpp/cwinapp-class_6.cpp)]  
  
##  <a name="getprofilebinary"></a>は  
 アプリケーションのレジストリの指定されたセクション内のエントリからバイナリ データを取得するには、このメンバー関数を呼び出すか。INI ファイルです。  
  
```  
BOOL GetProfileBinary(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPBYTE* ppData,  
    UINT* pBytes);
```  
  
### <a name="parameters"></a>パラメーター  
 *大文字、小文字*  
 エントリがあるセクションを指定する NULL で終わる文字列へのポインター。  
  
 *lpszEntry*  
 値を取得するエントリを指定する NULL で終わる文字列へのポインター。  
  
 *ppData*  
 データのアドレスを受け取るポインターへのポインター。  
  
 *ペタバイト*  
 バイト単位でデータのサイズを受け取る UINT へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数はそのため、大文字小文字が区別されていない文字列で、*大文字、小文字*と*lpszEntry*パラメーターのどちらでもかまいません。  
  
> [!NOTE]
> **GetProfileBinary**はバッファーを割り当ててでそのアドレスを返します\* *ppData*します。 使用して、バッファーを解放するため、呼び出し元が**delete[]**します。  
  
> [!IMPORTANT]
>  この関数が返すデータは、NULL で終わるデータとは限らないため、呼び出し元で検証を行う必要があります。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&41;](../../mfc/reference/codesnippet/cpp/cwinapp-class_7.cpp)]  
  
 たとえば、次を参照してください。 [CWinApp::WriteProfileBinary](#writeprofilebinary)します。  
  
##  <a name="getprofileint"></a>は  
 アプリケーションのレジストリまたは .INI ファイルの指定のセクション内のエントリから整数値を取得します。  
  
```  
UINT GetProfileInt(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    int nDefault);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszSection`  
 エントリがあるセクションを指定する NULL で終わる文字列へのポインター。  
  
 `lpszEntry`  
 値を取得するエントリを指定する NULL で終わる文字列へのポインター。  
  
 `nDefault`  
 フレームワークがエントリを見つけられなかったときのために指定する既定値。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、指定されたエントリに続く文字列の整数値を返します。 エントリが見つからなかった場合は、パラメーター `nDefault` の値を返します。 指定されたエントリに対応する値が整数でない場合は、0 を返します。  
  
 このメンバー関数は .INI ファイル内の値として&16; 進表記をサポートします。 符号付き整数を取得したときは、`int` にキャストしてください。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、大文字、小文字の区別をしないので、`lpszSection` と `lpszEntry` の文字列は大文字、小文字のどちらでもかまいません。  
  
> [!IMPORTANT]
>  この関数が返すデータは、NULL で終わるデータとは限らないため、呼び出し元で検証を行う必要があります。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&42;](../../mfc/reference/codesnippet/cpp/cwinapp-class_8.cpp)]  
  
 たとえば、次を参照してください。 [cwinapp::writeprofileint](#writeprofileint)します。  
  
##  <a name="getprofilestring"></a>CWinApp::GetProfileString  
 アプリケーションのレジストリで指定されたセクション内のエントリに関連付けられている文字列を取得するには、このメンバー関数を呼び出すか。INI ファイルです。  
  
```  
CString GetProfileString(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszDefault = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszSection`  
 エントリがあるセクションを指定する NULL で終わる文字列へのポインター。  
  
 `lpszEntry`  
 ウィンドウの文字列を取得するエントリを含む null で終わる文字列へのポインター。 この値である必要があります**NULL**します。  
  
 `lpszDefault`  
 初期化ファイルにエントリが見つからない場合は、指定されたエントリの既定の文字列値を指します。  
  
### <a name="return-value"></a>戻り値  
 戻り値は、アプリケーションの文字列です。INI ファイルまたは`lpszDefault`文字列が見つからない場合。 フレームワークでサポートされる文字列の最大長は`_MAX_PATH`です。 場合`lpszDefault`は**NULL**、戻り値は空の文字列です。  
  
### <a name="remarks"></a>コメント  
  
> [!IMPORTANT]
>  この関数が返すデータは、NULL で終わるデータとは限らないため、呼び出し元で検証を行う必要があります。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&43;](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 別の例の例を参照してください。[は](#getprofileint)です。  
  
##  <a name="getsectionkey"></a>CWinApp::GetSectionKey  
 HKEY_CURRENT_USER のキーを返す\\「ソフトウェア」\RegistryKey\AppName\lpszSection します。  
  
```  
HKEY GetSectionKey(
LPCTSTR lpszSection,  
CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszSection`  
 取得するキーの名前。  
  
 `pTM`  
 ポインター、`CAtlTransactionManager`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 セクションのキー、関数が成功した場合それ以外の場合`NULL`します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hideapplication"></a>CWinApp::HideApplication  
 開いているドキュメントを閉じる前にアプリケーションを非表示にするには、このメンバー関数を呼び出します。  
  
```  
void HideApplication();
```  
  
##  <a name="htmlhelp"></a>CWinApp::HtmlHelp  
 Html ヘルプ アプリケーションを起動するには、このメンバー関数を呼び出します。  
  
```  
virtual void HtmlHelp(
    DWORD_PTR dwData,  
    UINT nCmd = 0x000F);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwData`  
 追加のデータを指定します。 使用される値の値に応じて異なります、`nCmd`パラメーター。  
  
 `nCmd`  
 要求されるヘルプの種類を指定します。 指定できる値とへの影響の一覧については、`dwData`パラメーターを参照してください、`uCommand`パラメーターでは、html ヘルプ API 関数の説明、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、html ヘルプ アプリケーションを起動するには、この関数も呼び出します。  
  
 フレームワークでは、アプリケーションの終了時に、html ヘルプ アプリケーションは自動的に閉じます。  
  
##  <a name="initinstance"></a>場合は  
 Windows には、同時に実行する同じプログラムの複数のコピーが許可されます。  
  
```  
virtual BOOL InitInstance();
```  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションの初期化が&2; つのセクションに分割します。&1; 回限りのアプリケーションの初期化は、最初に行われるとき、プログラムの実行と、時刻の最初の時間を含むプログラムの実行のコピーのそれぞれを実行しているインスタンスを初期化します。 フレームワークの実装の`WinMain`この関数を呼び出します。  
  
 オーバーライド`InitInstance`を Windows で実行されているアプリケーションの新しいインスタンスを初期化します。 通常をオーバーライドする`InitInstance`メイン ウィンドウ オブジェクトを構築し、設定、`CWinThread::m_pMainWnd`そのウィンドウを指すデータ メンバーです。 このメンバー関数のオーバーライドの詳細については、次を参照してください。 [CWinApp: アプリケーション クラス](../../mfc/cwinapp-the-application-class.md)します。  
  
> [!NOTE]
>  MFC アプリケーションは、シングルスレッド アパートメント (STA) として初期化する必要があります。 呼び出した場合[CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279)で、`InitInstance`指定をオーバーライド`COINIT_APARTMENTTHREADED`(なく`COINIT_MULTITHREADED`)。 詳細については、[prb] を参照してください: MFC アプリケーションとして、マルチ スレッド アパートメント (828643) でアプリケーションを初期化するときの応答を停止[http://support.microsoft.com/default.aspxscid=kb;en-us;828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCListView&#9;](../../atl/reference/codesnippet/cpp/cwinapp-class_10.cpp)]  
  
##  <a name="istaskbarinteractionenabled"></a>CWinApp::IsTaskbarInteractionEnabled  
 Windows 7 タスクバーの相互作用が有効になっているかどうかを指示します。  
  
```  
virtual BOOL IsTaskbarInteractionEnabled();
```  
  
### <a name="return-value"></a>戻り値  
 返します。`TRUE`場合`EnableTaskbarInteraction`が呼び出されたオペレーティング システムが Windows 7 以降。  
  
### <a name="remarks"></a>コメント  
 タスク バーの相互作用は、マウス ポインターがアプリケーションのタスク バー ボタンの上にあるときに表示される別のタブ付きのサムネイルで MDI アプリケーションが MDI 子ウィンドウの内容を表示することを意味します。  
  
##  <a name="loadcursor"></a>CWinApp::LoadCursor  
 によって指定されたカーソルのリソースを読み込みます`lpszResourceName`またはによって指定された`nIDResource`現在の実行可能ファイルからです。  
  
```  
HCURSOR LoadCursor(LPCTSTR lpszResourceName) const;  HCURSOR LoadCursor(UINT nIDResource) const;  ```  
  
### Parameters  
 `lpszResourceName`  
 Points to a null-terminated string that contains the name of the cursor resource. You can use a `CString` for this argument.  
  
 `nIDResource`  
 ID of the cursor resource. For a list of resources, see [LoadCursor](http://msdn.microsoft.com/library/windows/desktop/ms648391) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Return Value  
 A handle to a cursor if successful; otherwise **NULL**.  
  
### Remarks  
 `LoadCursor` loads the cursor into memory only if it has not been previously loaded; otherwise, it retrieves a handle of the existing resource.  
  
 Use the [LoadStandardCursor](#loadstandardcursor) or [LoadOEMCursor](#loadoemcursor) member function to access the predefined Windows cursors.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#44](../../mfc/reference/codesnippet/cpp/cwinapp-class_11.cpp)]  
  
##  <a name="loadicon"></a>  CWinApp::LoadIcon  
 Loads the icon resource named by `lpszResourceName` or specified by `nIDResource` from the executable file.  
  
```  
HICON LoadIcon(LPCTSTR lpszResourceName) const です。 HICON LoadIcon(UINT nIDResource) const です。 ```  
  
### <a name="parameters"></a>パラメーター  
 `lpszResourceName`  
 アイコン リソースの名前を表す null で終わる文字列へのポインター。 使用することも、`CString`この引数です。  
  
 `nIDResource`  
 アイコン リソースの ID 番号。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、アイコンを識別するハンドルそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 `LoadIcon`それが読み込まれていない以前; 場合にのみ、アイコンを読み込みますそれ以外の場合、既存のリソースのハンドルを取得します。  
  
 使用することができます、 [LoadStandardIcon](#loadstandardicon)または[LoadOEMIcon](#loadoemicon)定義済みの Windows アイコンにアクセスするメンバー関数。  
  
> [!NOTE]
>  このメンバー関数は、Win32 API 関数を呼び出して[LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072)に準拠しているサイズのアイコンをのみ読み込むことができますが、 **SM_CXICON**と**SM_CYICON**システム メトリックの値。  
  
##  <a name="loadoemcursor"></a>CWinApp::LoadOEMCursor  
 定義済みで指定されたカーソルのリソースの読み込み、Windows`nIDCursor`します。  
  
```  
HCURSOR LoadOEMCursor(UINT nIDCursor) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDCursor`  
 **OCR_**マニフェストの定義済みの Windows カーソルを指定する定数の識別子。 必要があります**#define OEMRESOURCE**する前に**#include \<afxwin.h >**にアクセスするために、 **OCR_** WINDOWS 内の定数です。H.  
  
### <a name="return-value"></a>戻り値  
 成功した場合、カーソルのハンドルそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 使用して、`LoadOEMCursor`または[LoadStandardCursor](#loadstandardcursor)定義済みの Windows cursor にアクセスするメンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&45;](../../mfc/reference/codesnippet/cpp/cwinapp-class_12.h)]  
  
 [!code-cpp[NVC_MFCWindowing&#46;](../../mfc/reference/codesnippet/cpp/cwinapp-class_13.cpp)]  
  
##  <a name="loadoemicon"></a>CWinApp::LoadOEMIcon  
 定義済みで指定されたアイコンのリソースの読み込み、Windows`nIDIcon`します。  
  
```  
HICON LoadOEMIcon(UINT nIDIcon) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDIcon`  
 **OIC_**マニフェストの定義済みの Windows アイコンを指定する定数の識別子。 必要があります**#define OEMRESOURCE**する前に**#include \<afxwin.h >**にアクセスする、 **OIC_** WINDOWS 内の定数です。H.  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、アイコンを識別するハンドルそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 使用して、`LoadOEMIcon`または[LoadStandardIcon](#loadstandardicon)定義済みの Windows アイコンにアクセスするメンバー関数。  
  
##  <a name="loadstandardcursor"></a>CWinApp::LoadStandardCursor  
 定義済みのカーソル リソースを読み込み、Windows を`lpszCursorName`を指定します。  
  
```  
HCURSOR LoadStandardCursor(LPCTSTR lpszCursorName) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszCursorName`  
 **Idc _**マニフェストの定義済みの Windows カーソルを指定する定数の識別子。 これらの識別子は、WINDOWS で定義されます。H. 次の一覧は、使用可能な定義済みの値との意味を示しています`lpszCursorName`:。  
  
- **IDC_ARROW**標準の矢印カーソル  
  
- **IDC_IBEAM**標準のテキスト挿入カーソル。  
  
- **IDC_WAIT** Windows が時間のかかるタスクを実行するときに使用する砂時計カーソル  
  
- **IDC_CROSS**十字カーソルの選択  
  
- **IDC_UPARROW**上向きの矢印  
  
- **IDC_SIZE**廃止し、サポートされていません使用**IDC_SIZEALL。**  
  
- **IDC_SIZEALL**&4; 方向矢印です。 使用して、ウィンドウのサイズを変更するカーソル。  
  
- **IDC_ICON** Obsolete とサポートされていません。 使用**IDC_ARROW**します。  
  
- **IDC_SIZENWSE**左と右下の両端に双方向の矢印  
  
- **IDC_SIZENESW**右方向と下の左上の両端に双方向の矢印  
  
- **IDC_SIZEWE**双方向の水平矢印  
  
- **IDC_SIZENS**垂直の両方向矢印  
  
### <a name="return-value"></a>戻り値  
 成功した場合、カーソルのハンドルそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 使用して、`LoadStandardCursor`または[LoadOEMCursor](#loadoemcursor)定義済みの Windows cursor にアクセスするメンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&47;](../../mfc/reference/codesnippet/cpp/cwinapp-class_14.cpp)]  
  
##  <a name="loadstandardicon"></a>CWinApp::LoadStandardIcon  
 定義済みのアイコン リソースを読み込み、Windows を`lpszIconName`を指定します。  
  
```  
HICON LoadStandardIcon(LPCTSTR lpszIconName) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszIconName`  
 定義済みの Windows アイコンを指定するマニフェスト定数の識別子。 これらの識別子は、WINDOWS で定義されます。H. 指定できる定義済みの値とその説明の一覧は、次を参照してください。、*されています*パラメーター [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、アイコンを識別するハンドルそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 使用して、`LoadStandardIcon`または[LoadOEMIcon](#loadoemicon)定義済みの Windows アイコンにアクセスするメンバー関数。  
  
##  <a name="loadstdprofilesettings"></a>既定  
 内からこのメンバー関数を呼び出して、 [InitInstance](#initinstance)を有効にして (MRU) の最近使用したファイルの一覧を読み込むし、最後の状態をプレビューするメンバー関数。  
  
```  
void LoadStdProfileSettings(UINT nMaxMRU = _AFX_MRU_COUNT);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMaxMRU`  
 追跡するために、最近使用したファイルの数。  
  
### <a name="remarks"></a>コメント  
 場合`nMaxMRU`は 0、MRU 一覧は維持されません。  
  
##  <a name="m_bhelpmode"></a>CWinApp::m_bHelpMode  
 **TRUE**場合は、アプリケーションは、ヘルプ コンテキスト モード (従来どおりで起動される shift キーを押しながら f1 キー)。 それ以外の場合**FALSE**します。  
  
```  
BOOL m_bHelpMode;  
```  
  
### <a name="remarks"></a>コメント  
 ヘルプ コンテキスト モードは、疑問符 () は、カーソルが、ユーザーを使用すると、画面は移動できます。 ヘルプ モードのときの特別な処理を実装する場合は、このフラグを調べてください。 `m_bHelpMode`型のパブリック変数**BOOL**します。  
  
##  <a name="m_dwrestartmanagersupportflags"></a>CWinApp::m_dwRestartManagerSupportFlags  
 再起動マネージャーの動作を決定するフラグです。  
  
```  
DWORD m_dwRestartManagerSupportFlags;  
```  
  
### <a name="remarks"></a>コメント  
 再起動マネージャーを有効にするには設定`m_dwRestartManagerSupportFlags`の必要な動作をします。 次の表は、使用できるフラグを示します。  
  
|||  
|-|-|  
|フラグ|説明|  
|`AFX_RESTART_MANAGER_SUPPORT_RESTART`|使用してアプリケーションを登録する[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)します。 再起動マネージャーは、予期せず終了した場合は、アプリケーションを再起動します。|  
|- `AFX_RESTART_MANAGER_SUPPORT_RECOVERY`|アプリケーションが再起動マネージャーに登録されており、アプリケーションを再起動する際、再起動マネージャーが回復コールバック関数を呼び出します。 既定の回復のコールバック関数は、 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)します。|  
|- `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`|自動保存が有効にし、再起動マネージャーによって自動保存、アプリケーションの再起動時に、開いているドキュメントです。|  
|- `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`|自動保存が有効にし、再起動マネージャーによって自動保存の開いているドキュメントを一定の間隔でします。 間隔が定義されている[CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)します。|  
|- `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`|再起動マネージャーは、予期しない終了からアプリケーションを再起動した後に開いていたドキュメントを開きます。 [CDataRecoveryHandler クラス](../../mfc/reference/cdatarecoveryhandler-class.md)開いているドキュメントの一覧を格納して、復元することを処理します。|  
|- `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`|再起動マネージャーは、アプリケーションの再起動後に自動保存されたファイルを復元するかどうかを求めるメッセージを表示します。 `CDataRecoveryHandler`クラスは、ユーザーを照会します。|  
|- `AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE`|和集合`AFX_RESTART_MANAGER_SUPPORT_RESTART`、 `AFX_RESTART_MANAGER_SUPPORT_RECOVER`、および`AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`です。|  
|- `AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS`|The union of `AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`, and `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`.|  
|- `AFX_RESTART_MANAGER_SUPPORT_RESTART_ASPECTS`|The union of `AFX_RESTART_MANAGER_SUPPORT_RESTART`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`, `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`, and `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`.|  
|- `AFX_RESTART_MANAGER_SUPPORT_RECOVERY_ASPECTS`|The union of `AFX_RESTART_MANAGER_SUPPORT_RECOVERY`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`, `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`, and `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`.|  
  
##  <a name="m_ehelptype"></a>CWinApp::m_eHelpType  
 このデータ メンバーの型は、列挙型**AFX_HELP_TYPE**、内で定義されている、`CWinApp`クラスです。  
  
```  
AFX_HELP_TYPE m_eHelpType;  
```  
  
### <a name="remarks"></a>コメント  
 **AFX_HELP_TYPE**列挙型が次のように定義されています。  
  
 `enum AFX_HELP_TYPE`  
  
 `{`  
  
 `afxWinHelp = 0,`  
  
 `afxHTMLHelp = 1`  
  
 `};`  
  
-   HTML ヘルプへのアプリケーションのヘルプを設定するには、呼び出す[として](#sethelpmode)指定**場合**します。  
  
-   WinHelp をアプリケーションのヘルプを設定するには、呼び出す`SetHelpMode`し指定**afxWinHelp**します。  
  
##  <a name="m_hinstance"></a>CWinApp::m_hInstance  
 対応する、`hInstance`を Windows で渡されるパラメーター`WinMain`します。  
  
```  
HINSTANCE m_hInstance;  
```  
  
### <a name="remarks"></a>コメント  
 `m_hInstance`データ メンバーは、Windows で実行されているアプリケーションの現在のインスタンスを識別するハンドル。 これは、グローバル関数によって返される[AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle)します。 `m_hInstance`型のパブリック変数`HINSTANCE`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&55;](../../mfc/reference/codesnippet/cpp/cwinapp-class_15.cpp)]  
  
##  <a name="m_lpcmdline"></a>CWinApp::m_lpCmdLine  
 対応する、`lpCmdLine`を Windows で渡されるパラメーター`WinMain`します。  
  
```  
LPTSTR m_lpCmdLine;  
```  
  
### <a name="remarks"></a>コメント  
 アプリケーションのコマンドラインを指定する null で終わる文字列へのポインター。 使用`m_lpCmdLine`ユーザーがアプリケーションを起動したときに入力したコマンドライン引数にアクセスします。 `m_lpCmdLine`型のパブリック変数`LPTSTR`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&52;](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]  
  
##  <a name="m_nautosaveinterval"></a>CWinApp::m_nAutosaveInterval  
 自動保存の間隔をミリ秒単位で時間の長さ。  
  
```  
int m_nAutosaveInterval;  
```  
  
### <a name="remarks"></a>コメント  
 設定された間隔では、開いているドキュメントの自動再起動マネージャーを構成できます。 アプリケーションが自動保存ファイルではない場合は、このパラメーターは影響を与えません。  
  
##  <a name="m_ncmdshow"></a>CWinApp::m_nCmdShow  
 対応する、`nCmdShow`を Windows で渡されるパラメーター`WinMain`します。  
  
```  
int m_nCmdShow;  
```  
  
### <a name="remarks"></a>コメント  
 渡す必要があります`m_nCmdShow`を呼び出したときに引数として[また](../../mfc/reference/cwnd-class.md#showwindow)アプリケーションのメイン ウィンドウにします。 `m_nCmdShow`型のパブリック変数`int`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&56;](../../mfc/reference/codesnippet/cpp/cwinapp-class_17.cpp)]  
  
##  <a name="m_pactivewnd"></a>先  
 このデータ メンバーを使用すると、OLE サーバー アプリケーション、インプレース アクティブ化されている OLE コンテナー アプリケーションのメイン ウィンドウへのポインターを格納できます。  
  
### <a name="remarks"></a>コメント  
 このデータ メンバーが場合**NULL**アプリケーションがアクティブではありません。  
  
 フレームワークは、フレーム ウィンドウは、インプレース OLE コンテナー アプリケーションによってアクティブ化されるときに、このメンバー変数を設定します。  
  
##  <a name="m_pdatarecoveryhandler"></a>CWinApp::m_pDataRecoveryHandler  
 アプリケーションのデータ回復ハンドラーへのポインター。  
  
```  
CDataRecoveryHandler* m_pDataRecoveryHandler;  
```  
  
### <a name="remarks"></a>コメント  
 アプリケーションのデータ回復のハンドラーは、開いているドキュメントと自動保存を監視します。 フレームワークでは、データ回復ハンドラーを使用して、アプリケーションが予期せず終了後に再起動すると、自動保存されたファイルを復元します。 詳細については、次を参照してください。 [CDataRecoveryHandler クラス](../../mfc/reference/cdatarecoveryhandler-class.md)します。  
  
##  <a name="m_pszappname"></a>CWinApp::m_pszAppName  
 アプリケーション名を示します。  
  
```  
LPCTSTR m_pszAppName;  
```  
  
### <a name="remarks"></a>コメント  
 アプリケーション名に渡されたパラメーターから取得できます、 [CWinApp](#cwinapp)コンス トラクター、または、指定しない場合、リソース文字列の ID を持つ**AFX_IDS_APP_TITLE**します。 リソースの アプリケーション名が見つからない場合は、プログラムの由来とします。EXE ファイル名です。  
  
 グローバル関数によって返される[AfxGetAppName](application-information-and-management.md#afxgetappname)します。 `m_pszAppName`型のパブリック変数**const char\***します。  
  
> [!NOTE]
>  値を割り当てる場合`m_pszAppName`ヒープに動的に割り当てる必要があります。 `CWinApp`デストラクター呼び出し**無料**と this ポインター ()。 使用する多くの`_tcsdup`() のランタイム ライブラリ関数、割り当てを行う。 また、新しい値を割り当てる前に、現在のポインターに関連付けられているメモリを解放します。 例:  
  
 [!code-cpp[NVC_MFCWindowing #&57;](../../mfc/reference/codesnippet/cpp/cwinapp-class_18.cpp)]  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&65;](../../mfc/reference/codesnippet/cpp/cwinapp-class_19.cpp)]  
  
##  <a name="m_pszexename"></a>CWinApp::m_pszExeName  
 拡張子のないアプリケーションの実行可能ファイルの名前を表します。  
  
```  
LPCTSTR m_pszExeName;  
```  
  
### <a name="remarks"></a>コメント  
 異なり[m_pszAppName](#m_pszappname)、この名前は空白を含めることはできません。 `m_pszExeName`型のパブリック変数**const char\***します。  
  
> [!NOTE]
>  値を割り当てる場合`m_pszExeName`ヒープに動的に割り当てる必要があります。 `CWinApp`デストラクター呼び出し**無料**と this ポインター ()。 使用する多くの`_tcsdup`() のランタイム ライブラリ関数、割り当てを行う。 また、新しい値を割り当てる前に、現在のポインターに関連付けられているメモリを解放します。 例:  
  
 [!code-cpp[NVC_MFCWindowing #&58;](../../mfc/reference/codesnippet/cpp/cwinapp-class_20.cpp)]  
  
##  <a name="m_pszhelpfilepath"></a>CWinApp::m_pszHelpFilePath  
 アプリケーションのヘルプ ファイルへのパスが含まれています。  
  
```  
LPCTSTR m_pszHelpFilePath;  
```  
  
### <a name="remarks"></a>コメント  
 既定では、フレームワークを初期化します`m_pszHelpFilePath`を使用してアプリケーションの名前に"です。HLP"を追加します。 ヘルプ ファイルの名前を変更するには、次のように設定します。`m_pszHelpFilePath`指定したヘルプ ファイルの完全な名前を表す文字列を指すようです。 これを行う便利な場所は、アプリケーションの[InitInstance](#initinstance)関数です。 `m_pszHelpFilePath`型のパブリック変数**const char\***します。  
  
> [!NOTE]
>  値を割り当てる場合`m_pszHelpFilePath`ヒープに動的に割り当てる必要があります。 `CWinApp`デストラクター呼び出し**無料**と this ポインター ()。 使用する多くの`_tcsdup`() のランタイム ライブラリ関数、割り当てを行う。 また、新しい値を割り当てる前に、現在のポインターに関連付けられているメモリを解放します。 例:  
  
 [!code-cpp[NVC_MFCWindowing #&59;](../../mfc/reference/codesnippet/cpp/cwinapp-class_21.cpp)]  
  
##  <a name="m_pszprofilename"></a>CWinApp::m_pszProfileName  
 アプリケーションの名前を表します。INI ファイルです。  
  
```  
LPCTSTR m_pszProfileName;  
```  
  
### <a name="remarks"></a>コメント  
 `m_pszProfileName`型のパブリック変数**const char\***します。  
  
> [!NOTE]
>  値を割り当てる場合`m_pszProfileName`ヒープに動的に割り当てる必要があります。 `CWinApp`デストラクター呼び出し**無料**と this ポインター ()。 使用する多くの`_tcsdup`() のランタイム ライブラリ関数、割り当てを行う。 また、新しい値を割り当てる前に、現在のポインターに関連付けられているメモリを解放します。 例:  
  
 [!code-cpp[NVC_MFCWindowing&#60;](../../mfc/reference/codesnippet/cpp/cwinapp-class_22.cpp)]  
  
##  <a name="m_pszregistrykey"></a>CWinApp::m_pszRegistryKey  
 レジストリまたは INI ファイルで、アプリケーション プロファイルの設定の保存場所を決定するために使用します。  
  
```  
LPCTSTR m_pszRegistryKey;  
```  
  
### <a name="remarks"></a>コメント  
 通常、このデータ メンバーは、読み取り専用として扱われます。  
  
-   レジストリ キー値が格納されます。 アプリケーション プロファイルの設定の名前が次のレジストリ キーに追加されます: HKEY_CURRENT_USER/ソフトウェア/LocalAppWizard で生成されるとします。  
  
 値を割り当てる場合`m_pszRegistryKey`ヒープに動的に割り当てる必要があります。 `CWinApp`デストラクター呼び出し**無料**と this ポインター ()。 使用する多くの`_tcsdup`() のランタイム ライブラリ関数、割り当てを行う。 また、新しい値を割り当てる前に、現在のポインターに関連付けられているメモリを解放します。 例:  
  
 [!code-cpp[NVC_MFCWindowing&#61;](../../mfc/reference/codesnippet/cpp/cwinapp-class_23.cpp)]  
  
##  <a name="m_pszappid"></a>CWinApp::m_pszAppID  
 アプリケーションのユーザーのモデル id です。  
  
```  
LPCTSTR m_pszAppID;  
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="oncontexthelp"></a>CWinApp::OnContextHelp  
 アプリケーション内で shift キーを押しながら F1 ヘルプを処理します。  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>コメント  
 追加する必要があります、`ON_COMMAND( ID_CONTEXT_HELP, OnContextHelp )`ステートメントを`CWinApp`メッセージ マップのクラスし、追加アクセラレータ テーブル エントリを通常 shift キーを押しながら F1 このメンバー関数を有効にすることもできます。  
  
 `OnContextHelp`ヘルプ モードにアプリケーションを配置します。 矢印と疑問符 () と、ユーザーがカーソルの変更はマウス ポインターを移動し、 ダイアログ ボックス、ウィンドウ、メニューのまたはコマンド ボタンを選択するマウスの左ボタンを押します。 このメンバー関数は、カーソルでは、オブジェクトのヘルプ コンテキストを取得し、そのヘルプ コンテキストに Windows 関数 WinHelp を呼び出します。  
  
##  <a name="onddecommand"></a>CWinApp::OnDDECommand  
 メイン フレーム ウィンドウは、DDE を受け取ると、フレームワークによって呼び出されますメッセージを実行します。  
  
```  
virtual BOOL OnDDECommand(LPTSTR lpszCommand);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszCommand*  
 アプリケーションによって受信 DDE コマンド文字列を指します。  
  
### <a name="return-value"></a>戻り値  
 コマンドが処理された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装で、セルの内容のコマンドは、ドキュメントを開くための要求である場合は、指定したドキュメントを開きます。 Windows のファイル マネージャーは、一般には、ユーザーがデータ ファイルをダブルクリックするとこのような DDE コマンド文字列の機能を送信します。 上書きの他の DDE を処理するには、この関数は、印刷コマンドなどのコマンドを実行します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&48;](../../mfc/reference/codesnippet/cpp/cwinapp-class_24.cpp)]  
  
##  <a name="onfilenew"></a>CWinApp::OnFileNew  
 実装して、`ID_FILE_NEW`コマンドです。  
  
```  
afx_msg void OnFileNew();
```  
  
### <a name="remarks"></a>コメント  
 追加する必要があります、`ON_COMMAND( ID_FILE_NEW, OnFileNew )`ステートメントを`CWinApp`クラスのメッセージ マップをこのメンバー関数を有効にします。 有効な場合、この関数は、新しいコマンドの実行を処理します。  
  
 参照してください[テクニカル ノート 22:](../../mfc/tn022-standard-commands-implementation.md)既定の動作と、このメンバー関数をオーバーライドする方法に関するガイダンスについてです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing 番号&49;](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing #&50;](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="onfileopen"></a>CWinApp::OnFileOpen  
 実装して、`ID_FILE_OPEN`コマンドです。  
  
```  
afx_msg void OnFileOpen();
```  
  
### <a name="remarks"></a>コメント  
 追加する必要があります、`ON_COMMAND( ID_FILE_OPEN, OnFileOpen )`ステートメントを`CWinApp`クラスのメッセージ マップをこのメンバー関数を有効にします。 有効な場合、この関数は、ファイルを開くコマンドの実行を処理します。  
  
 既定の動作と、この関数をオーバーライドする方法については、次を参照してください。[テクニカル ノート 22:](../../mfc/tn022-standard-commands-implementation.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing 番号&49;](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing #&50;](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="onfileprintsetup"></a>CWinApp::OnFilePrintSetup  
 実装して、 **ID_FILE_PRINT_SETUP**コマンドです。  
  
```  
afx_msg void OnFilePrintSetup();
```  
  
### <a name="remarks"></a>コメント  
 追加する必要があります、`ON_COMMAND( ID_FILE_PRINT_SETUP, OnFilePrintSetup )`ステートメントを`CWinApp`クラスのメッセージ マップをこのメンバー関数を有効にします。 有効な場合、この関数は、ファイルの印刷コマンドの実行を処理します。  
  
 既定の動作と、この関数をオーバーライドする方法については、次を参照してください。[テクニカル ノート 22:](../../mfc/tn022-standard-commands-implementation.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing 番号&49;](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing #&50;](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="onhelp"></a>:Onhelp  
 アプリケーション内で F1 ヘルプを (現在のコンテキストを使って) 処理します。  
  
```  
afx_msg void OnHelp();
```  
  
### <a name="remarks"></a>コメント  
 通常 F1 キーを押すのアクセラレータ キーのエントリも追加します。 F1 キーを有効にするとは、要件ではありません、規則だけです。  
  
 追加する必要があります、`ON_COMMAND( ID_HELP, OnHelp )`ステートメントを`CWinApp`クラスのメッセージ マップをこのメンバー関数を有効にします。 有効な場合は、F1 キーを押したときに、フレームワークによって呼び出されます。  
  
 このメッセージ ハンドラー関数の既定の実装では、現在のウィンドウ、ダイアログ ボックスで、またはメニュー項目に対応しており、WINHELP を呼び出すためのヘルプ コンテキストを決定します。EXE します。 現在利用可能なコンテキストがない場合は、既定のコンテキストを使用します。  
  
 ウィンドウ、ダイアログ ボックス、メニュー項目またはフォーカスが置かれているツール バー ボタン以外に何かのヘルプ コンテキストを設定するには、この関数をオーバーライドします。 呼び出す`WinHelp`目的のヘルプ コンテキスト id。  
  
##  <a name="onhelpfinder"></a>CWinApp::OnHelpFinder  
 処理、 **ID_HELP_FINDER**と**ID_DEFAULT_HELP**コマンドです。  
  
```  
afx_msg void OnHelpFinder();
```  
  
### <a name="remarks"></a>コメント  
 追加する必要があります、`ON_COMMAND( ID_HELP_FINDER, OnHelpFinder )`ステートメントを`CWinApp`クラスのメッセージ マップをこのメンバー関数を有効にします。 アプリケーションのユーザーが呼び出しを検索するコマンドを選択したときにフレームワークによってこのメッセージ処理関数が有効な場合`WinHelp`標準**メニュー**トピックです。  
  
##  <a name="onhelpindex"></a>CWinApp::OnHelpIndex  
 処理、 **ID_HELP_INDEX**コマンドを使用し、既定のヘルプ トピックを提供します。  
  
```  
afx_msg void OnHelpIndex();
```  
  
### <a name="remarks"></a>コメント  
 追加する必要があります、`ON_COMMAND( ID_HELP_INDEX, OnHelpIndex )`ステートメントを`CWinApp`クラスのメッセージ マップをこのメンバー関数を有効にします。 アプリケーションのユーザーが呼び出すヘルプ コマンドを選択したときにフレームワークによってこのメッセージ処理関数が有効な場合`WinHelp`標準**メニュー**トピックです。  
  
##  <a name="onhelpusing"></a>CWinApp::OnHelpUsing  
 処理、 **ID_HELP_USING**コマンドです。  
  
```  
afx_msg void OnHelpUsing();
```  
  
### <a name="remarks"></a>コメント  
 追加する必要があります、`ON_COMMAND( ID_HELP_USING, OnHelpUsing )`ステートメントを`CWinApp`クラスのメッセージ マップをこのメンバー関数を有効にします。 フレームワークが、アプリケーションのユーザーが呼び出すヘルプを使用してコマンドを選択したときにこのメッセージ ハンドラー関数を呼び出す、`WinHelp`標準アプリケーション**有効**トピックです。  
  
##  <a name="onidle"></a>CWinApp::OnIdle  
 アイドル状態時の処理を実行するには、このメンバー関数をオーバーライドします。  
  
```  
virtual BOOL OnIdle(LONG lCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `lCount`  
 カウンターは毎回増加`OnIdle`アプリケーションのメッセージ キューが空のときに呼び出されます。 この数は、新しいメッセージが処理されるたびに 0 にリセットされます。 使用することができます、`lCount`パラメーターをメッセージを処理することがなく、アプリケーションであったアイドル時間の相対的な長さを決定します。  
  
### <a name="return-value"></a>戻り値  
 さらにアイドル処理時間を受信する 0 以外の値これ以上のアイドル時間が必要な場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `OnIdle`アプリケーションのメッセージ キューが空とき、既定のメッセージ ループで呼び出されます。 これらに上書きを使用して、独自の背景にアイドル処理を呼び出します。  
  
 `OnIdle`アイドル状態の処理時間が必要ないことを示すために 0 を返すはずです。 `lCount`パラメーターはたびに増分`OnIdle`メッセージ キューが空であり、新しいメッセージが処理されるたびに 0 にリセット時に呼び出されます。 この数に基づく、別のアイドル処理ルーチンを呼び出すことができます。  
  
 アイドル ループ処理を以下に示します。  
  
1.  Microsoft Foundation Class ライブラリにメッセージ ループが、メッセージ キューをチェックして、保留中のメッセージを検索しない場合は呼び出します`OnIdle`アプリケーション オブジェクトおよび装置 0 として、`lCount`引数。  
  
2. `OnIdle`いくつかの処理を実行し、取得を行うには&0; 以外の値を示すをもう一度呼び出す必要がさらに処理します。  
  
3.  メッセージ ループは、メッセージ キューをもう一度確認します。 保留中のメッセージがない場合は、呼び出す`OnIdle`、インクリメント、`lCount`引数。  
  
4.  最終的には、`OnIdle`アイドル状態のすべてのタスクの処理が完了すると、0 を返します。 これにより、メッセージ ループの呼び出しを停止する`OnIdle`メッセージ キューから次のメッセージを受信するまでこの時点でアイドル状態にサイクルが再開引数を 0 に設定します。  
  
 時に、時間のかかるタスクを実行しないで`OnIdle`アプリケーションまでのユーザー入力を処理できないので`OnIdle`を返します。  
  
> [!NOTE]
>  既定の実装`OnIdle`更新プログラムは、メニュー項目とツール バー ボタンなどのユーザー インターフェイス オブジェクトをコマンドを使用し、内部データ構造の後処理を行います。 そのため、オーバーライドする場合は`OnIdle`、呼び出す必要があります`CWinApp::OnIdle`で、`lCount`オーバーライドされたバージョンでします。 最初にアイドル処理のすべての基本クラスを呼び出します (つまり、基本クラスまで`OnIdle`0 を返します)。 基本クラスの処理が完了していなかった作業を実行する必要がある場合を確認して、適切な基本クラスの実装`lCount`する作業を行います。  
  
 たくない場合`OnIdle`にするには、メッセージ キューからメッセージを取得するたびに呼び出されると、オーバーライド、 [CWinThreadIsIdleMessage](../../mfc/reference/cwinthread-class.md#isidlemessage)します。 アプリケーションが非常に短い時間のタイマーを設定した場合、またはシステムが送信する場合、**とき**メッセージ、`OnIdle`は繰り返し呼び出され、パフォーマンスが低下します。  
  
### <a name="example"></a>例  
 次の&2; つの例は、使用する方法を示して`OnIdle`します。 最初の例を使用して&2; つのアイドル状態のタスクを処理して、`lCount`優先処理に渡す引数。 最初のタスクは優先度の高いと、可能な限りそれを行う必要があります。 2 番目のタスクは、重要度の低いユーザー入力を一時停止時間がある場合にのみ行う必要があります。 基底クラス版への呼び出しに注意してください`OnIdle`します。 2 番目の例では、さまざまな優先順位がアイドル状態のタスクのグループを管理します。  
  
 [!code-cpp[NVC_MFCWindowing&51;](../../mfc/reference/codesnippet/cpp/cwinapp-class_27.cpp)]  
  
##  <a name="opendocumentfile"></a>:Opendocumentfile  
 フレームワークは、このメソッドを開くには、名前付き[CDocument](../../mfc/reference/cdocument-class.md)アプリケーションのファイルです。  
  
```  
virtual CDocument* OpenDocumentFile(
LPCTSTR lpszFileName  
BOOL bAddToMRU = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszFileName`  
 開かれるファイルの名前。  
  
 [入力] `bAddToMRU`  
 `TRUE`ドキュメントが最新のファイルのいずれかを示します`FALSE`ドキュメントが最新のファイルのいずれかを示します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CDocument`成功した場合は`NULL`です。  
  
### <a name="remarks"></a>コメント  
 その名前を持つドキュメントが既に開いている場合、そのドキュメントが含まれる最初のフレーム ウィンドウは、フォーカスを取得します。 アプリケーションでは、複数のドキュメント テンプレートをサポートする場合、フレームワークは、ドキュメントの読み込みしようとする適切なドキュメント テンプレートを検索するファイル名拡張子を使用します。 成功した場合、ドキュメント テンプレートし、フレーム ウィンドウとドキュメントのビューが作成されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&52;](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]  
  
##  <a name="parsecommandline"></a>CWinApp::ParseCommandLine  
 コマンドラインを解析し、1 つずつ、パラメーターに送信するには、このメンバー関数を呼び出して[後](../../mfc/reference/ccommandlineinfo-class.md#parseparam)します。  
  
```  
void ParseCommandLine(CCommandLineInfo& rCmdInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `rCmdInfo`  
 参照、[メンバー](../../mfc/reference/ccommandlineinfo-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 アプリケーション ウィザードでのローカル インスタンスを作成するアプリケーションのウィザードを使用して新しい MFC プロジェクトを開始すると`CCommandLineInfo`、まず`ProcessShellCommand`と`ParseCommandLine`で、 [InitInstance](#initinstance)メンバー関数。 コマンド ラインは、以下に説明を次に示します。  
  
1.  後で作成されている`InitInstance`、`CCommandLineInfo`に渡されるオブジェクト`ParseCommandLine`します。  
  
2. `ParseCommandLine`呼び出して`CCommandLineInfo::ParseParam`繰り返し、各パラメーターに対して&1; 回です。  
  
3. `ParseParam`入力、`CCommandLineInfo`オブジェクトに渡されます[によって](#processshellcommand)します。  
  
4. `ProcessShellCommand`コマンドライン引数とフラグを処理します。  
  
 呼び出すことのできる注`ParseCommandLine`必要に応じて、直接します。  
  
 コマンド ライン フラグの説明は、次を参照してください。 [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand)します。  
  
##  <a name="pretranslatemessage"></a>Cwinapp::pretranslatemessage  
 Windows 関数にディスパッチされる前に、ウィンドウ メッセージをフィルター処理するには、この関数をオーバーライド[TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934)呼び出す必要がありますので、既定の実装は、アクセラレータ キーに変換を実行、`CWinApp::PreTranslateMessage`オーバーライドされたバージョンのメンバー関数。  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMsg`  
 ポインター、 [MSG](../../mfc/reference/msg-structure1.md)処理するメッセージを格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 メッセージを完全に処理された場合は&0; 以外`PreTranslateMessage`し、さらに処理する必要があります。 メッセージは、通常どおりに処理必要がある場合は&0; を返します。  
  
##  <a name="processmessagefilter"></a>CWinApp::ProcessMessageFilter  
 フレームワークのフック関数は、フィルター処理し、特定の Windows メッセージに応答するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL ProcessMessageFilter(
    int code,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 `code`  
 フック コードを指定します。 このメンバー関数では、コードを使用して、処理する方法を決定します。`lpMsg.`  
  
 `lpMsg`  
 Windows へのポインター [MSG](../../mfc/reference/msg-structure1.md)構造体。  
  
### <a name="return-value"></a>戻り値  
 メッセージが処理された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 フック関数の処理、アプリケーションの通常のメッセージに送信する前にイベントを処理します。  
  
 この高度な機能をオーバーライドする場合は、フレームワークを維持するために基本クラスのバージョンを呼び出すことを確認する処理をフックします。  
  
##  <a name="processshellcommand"></a>CWinApp::ProcessShellCommand  
 によって呼び出されます[InitInstance](#initinstance)から渡されたパラメーターを受け入れるように、`CCommandLineInfo`で識別されるオブジェクト`rCmdInfo`、指定された操作を実行します。  
  
```  
BOOL ProcessShellCommand(CCommandLineInfo& rCmdInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `rCmdInfo`  
 参照、[メンバー](../../mfc/reference/ccommandlineinfo-class.md)オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、シェル コマンドが正常に処理されます。 0 の場合、返す**FALSE**から[InitInstance](#initinstance)します。  
  
### <a name="remarks"></a>コメント  
 アプリケーション ウィザードでのローカル インスタンスを作成するアプリケーションのウィザードを使用して新しい MFC プロジェクトを開始するときに`CCommandLineInfo`、まず`ProcessShellCommand`と[ParseCommandLine](#parsecommandline)で、`InitInstance`メンバー関数。 コマンド ラインは、以下に説明を次に示します。  
  
1.  後で作成されている`InitInstance`、`CCommandLineInfo`に渡されるオブジェクト`ParseCommandLine`します。  
  
2. `ParseCommandLine`呼び出して[後](../../mfc/reference/ccommandlineinfo-class.md#parseparam)繰り返し、各パラメーターに対して&1; 回です。  
  
3. `ParseParam`入力、`CCommandLineInfo`オブジェクトに渡されます`ProcessShellCommand`します。  
  
4. `ProcessShellCommand`コマンドライン引数とフラグを処理します。  
  
 データ メンバー、`CCommandLineInfo`で識別されるオブジェクト[CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand)、次の列挙型内で定義されているは、`CCommandLineInfo`クラスです。  
  
 `enum {`  
  
 `FileNew,`  
  
 `FileOpen,`  
  
 `FilePrint,`  
  
 `FilePrintTo,`  
  
 `FileDDE,`  
  
 `};`  
  
 これらの各値の簡単な説明を参照してください。`CCommandLineInfo::m_nShellCommand`します。  
  
##  <a name="processwndprocexception"></a>CWinApp::ProcessWndProcException  
 フレームワークは、ハンドラーがアプリケーションのメッセージ、またはコマンド ハンドラーのいずれかでスローされる例外をキャッチしないときに、このメンバー関数を呼び出します。  
  
```  
virtual LRESULT ProcessWndProcException(
    CException* e,  
    const MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 *e*  
 キャッチされない例外へのポインター。  
  
 `pMsg`  
 A [MSG](../../mfc/reference/msg-structure1.md)フレームワークが例外をスローする原因となった windows メッセージに関する情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 この値は、Windows に戻してください。 通常この値を windows メッセージを 1 L ( **TRUE**) コマンド メッセージのです。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を直接呼び出さないでください。  
  
 このメンバー関数の既定の実装では、メッセージ ボックスを作成します。 メッセージ ボックス、メニューのツールバー、またはアクセラレータ コマンドのエラーをキャッチされない例外の作成元;「コマンドが失敗しました」メッセージが表示されます。それ以外の場合、「内部アプリケーション エラー」メッセージが表示されます。  
  
 グローバルに、例外の処理を提供するには、この関数をオーバーライドします。 メッセージ ボックスを表示したい場合は、基本機能を呼び出すのみです。  
  
##  <a name="register"></a>CWinApp::Register  
 登録タスクで処理されない実行`RegisterShellFileTypes`します。  
  
```  
virtual BOOL Register();
```  
  
### <a name="return-value"></a>戻り値  
 正常に完了した場合はゼロ以外、それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 既定の実装は、単に TRUE を返します。 カスタマイズした登録手順を提供するには、この関数をオーバーライドします。  
  
##  <a name="registershellfiletypes"></a>登録  
 Windows ファイル マネージャーですべてのアプリケーションのドキュメントの種類を登録するには、このメンバー関数を呼び出します。  
  
```  
void RegisterShellFileTypes(BOOL bCompat = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bCompat`  
 `TRUE`シェル コマンドの印刷と印刷が、許可またはプリンター オブジェクトに、ファイルをドラッグして、シェルから直接ファイルを印刷するユーザーの登録エントリを追加します。 また、DefaultIcon キーを追加します。 このパラメーターは、既定では、`FALSE`旧バージョンとの互換性のためです。  
  
### <a name="remarks"></a>コメント  
 これにより、ユーザーをダブルクリックしてからファイル マネージャー内で、アプリケーションで作成されたデータ ファイルを開くことです。 呼び出す`RegisterShellFileTypes`を呼び出した後[ごと](#adddoctemplate)アプリケーションのドキュメント テンプレートごとです。 呼び出すことも、 [EnableShellOpen](#enableshellopen)メンバー関数を呼び出したときに`RegisterShellFileTypes`します。  
  
 `RegisterShellFileTypes`リストを反復処理[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)アプリケーションの維持し、それぞれのドキュメント テンプレートのファイルの関連付けを管理するとき Windows 登録データベースにエントリを追加するオブジェクトします。 ファイル マネージャーでは、これらのエントリを使用して、ユーザーがダブルクリックしたときに、データ ファイルを開きます。 これを出荷する必要がある、します。REG ファイルとアプリケーション。  
  
> [!NOTE]
> `RegisterShellFileTypes`ユーザーが管理者権限を持つプログラムを実行する場合にのみ機能します。 プログラムが管理者権限を持っていない場合のレジストリ キーを変更することはできません。  
  
 登録情報データベースは、既に別のファイル形式に指定したファイル名拡張子を関連付けます、新しい関連付けは作成されません。 参照してください、`CDocTemplate`この情報を登録するために必要な文字列の形式のクラスです。  
  
##  <a name="registerwithrestartmanager"></a>CWinApp::RegisterWithRestartManager  
 再起動マネージャーとのアプリケーションを登録します。  
  
```  
virtual HRESULT RegisterWithRestartManager(
BOOL bRegisterRecoveryCallback,  
const CString& strRestartIdentifier);

 
virtual HRESULT RegisterWithRestartManager(
LPCWSTR pwzCommandLineArgs,  
DWORD dwRestartFlags,  
APPLICATION_RECOVERY_CALLBACK pRecoveryCallback,  
LPVOID lpvParam,  
DWORD dwPingInterval,  
DWORD dwCallbackFlags);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `bRegisterRecoveryCallback`|`TRUE`回復のコールバック関数を使用して、アプリケーションのこのインスタンスを示します`FALSE`実装していないことを示します。 フレームワークは、アプリケーションが予期せず終了したときに、回復のコールバック関数を呼び出します。 詳細については、次を参照してください。 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)します。|  
|[入力] `strRestartIdentifier`|再起動マネージャーのインスタンスを識別する一意の文字列。 再起動マネージャーの識別子は、アプリケーションの各インスタンスに一意です。|  
|[入力] `pwzCommandLineArgs`|コマンドラインから余分な引数を表す文字列。|  
|[入力] `dwRestartFlags`|再起動マネージャーのオプション フラグ。 詳細については、「解説」を参照してください。|  
|[入力] `pRecoveryCallback`|回復のコールバック関数。 この関数を取る必要があります、`LPVOID`パラメーターと戻り値を入力として、`DWORD`です。 既定の回復のコールバック関数は、`CWinApp::ApplicationRecoveryCallback`です。|  
|[入力] `lpvParam`|回復のコールバック関数の入力パラメーター。 詳細については、次を参照してください。 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)します。|  
|[入力] `dwPingInterval`|再起動マネージャーが回復コールバック関数が返すまで待機する時間の長さ。 このパラメーターはミリ秒です。|  
|[入力] `dwCallbackFlags`|フラグは、回復のコールバック関数に渡されます。 将来使用するために予約されています。|  
  
### <a name="return-value"></a>戻り値  
 `S_OK`メソッドが成功した場合それ以外の場合はエラー コード。  
  
### <a name="remarks"></a>コメント  
 単純なバージョンを使用する場合は、アプリケーションでは、既定の MFC 実装を使用してファイルを自動保存、する必要があります`RegisterWithRestartManager`します。 複雑なバージョンの使用`RegisterWithRestartManager`アプリケーションの自動保存の動作をカスタマイズする場合。  
  
 空の文字列では、このメソッドを呼び出すかどうか`strRestartIdentifier`、`RegisterWithRestartManager`マネージャーを再起動のこのインスタンスの一意の識別子の文字列を作成します。  
  
 アプリケーションが予期せず終了したときに、再起動マネージャーは、コマンドラインからアプリケーションを再起動し、一意の再起動オプションの引数としての識別子を提供します。 このシナリオでは、フレームワーク`RegisterWithRestartManager`2 回です。 最初の呼び出し元が[場合は](#initinstance)文字列識別子の空の文字列を使用します。 メソッドではその後、 [CWinApp::ProcessShellCommand](#processshellcommand)呼び出し`RegisterWithRestartManager`一意の再起動の識別子を使用します。  
  
 再起動マネージャーとのアプリケーションを登録した後、再起動マネージャーは、アプリケーションを監視します。 アプリケーションが予期せず終了した場合、再起動マネージャーは、シャット ダウン処理中に回復コールバック関数を呼び出します。 再起動マネージャーの待機、`dwPingInterval`回復コールバック関数からの応答。 回復のコールバック関数がこの時間内に応答しない場合は、回復コールバック関数を実行することがなく、アプリケーションが終了します。  
  
 既定では、dwRestartFlags はサポートされていませんが、将来使用するために提供されます。 ような値`dwRestartFlags`は次のようになります。  
  
- `RESTART_NO_CRASH`  
  
- `RESTART_NO_HANG`  
  
- `RESTART_NO_PATCH`  
  
- `RESTART_NO_REBOOT`  
  
##  <a name="reopenpreviousfilesatrestart"></a>CWinApp::ReopenPreviousFilesAtRestart  
 再起動マネージャーが、アプリケーションが予期せず終了したときに開いていたファイルを開くかどうかを決定します。  
  
```  
virtual BOOL ReopenPreviousFilesAtRestart() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`再起動マネージャー再度開いていたファイルを示します`FALSE`再起動マネージャーがいないことを示します。  
  
##  <a name="restartinstance"></a>CWinApp::RestartInstance  
 再起動マネージャーによって開始されたアプリケーションの再起動を処理します。  
  
```  
virtual BOOL CWinApp::RestartInstance();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`データ回復のハンドラーを開いている場合のドキュメントに開かれていた`FALSE`データ復元ハンドラーにエラーがある場合、または既に開いているドキュメントはありません。  
  
### <a name="remarks"></a>コメント  
 再起動マネージャーは、アプリケーションを再起動するときに、フレームワークは、このメソッドを呼び出します。 このメソッドは、データ回復のハンドラーを取得し、自動保存されたファイルを復元します。 このメソッドを呼び出す[CDataRecoveryHandler::RestoreAutosavedDocuments](../../mfc/reference/cdatarecoveryhandler-class.md#restoreautosaveddocuments)をユーザーが自動保存されたファイルを復元するかどうかを判断します。  
  
 このメソッドが戻る`FALSE`場合、 [CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md)開いているドキュメントが含まれていなかったことを決定します。 開いているドキュメントがない場合、アプリケーションは通常どおりに起動します。  
  
##  <a name="restoreautosavedfilesatrestart"></a>CWinApp::RestoreAutosavedFilesAtRestart  
 再起動マネージャーが、アプリケーションを再起動する際に、自動保存されたファイルを復元するかどうかを決定します。  
  
```  
virtual BOOL RestoreAutosavedFilesAtRestart() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`再起動マネージャーのリストア自動保存されたファイルを示します`FALSE`再起動マネージャーがいないことを示します。  
  
##  <a name="run"></a>:Run  
 既定のメッセージ ループを提供します。  
  
```  
virtual int Run();
```  
  
### <a name="return-value"></a>戻り値  
 `int`によって返される値`WinMain`です。  
  
### <a name="remarks"></a>コメント  
 **実行**を取得し、アプリケーションが受信するまでに Windows メッセージをディスパッチ、 **WM_QUIT**メッセージです。 アプリケーションのメッセージ キューにメッセージがない場合**実行**呼び出し[OnIdle](#onidle)アイドル時間の処理を実行します。 受信メッセージ、 [PreTranslateMessage](#pretranslatemessage)特別な処理され、次に、メンバー関数**TranslateMessage**標準キーボードの翻訳の最後に、 **DispatchMessage** Windows 関数が呼び出されます。  
  
 **実行**オーバーライドされることはほとんどありませんが特別な動作を提供するメソッドをオーバーライドすることができます。  
  
##  <a name="runautomated"></a>CWinApp::RunAutomated  
 判断するには、この関数を呼び出すかどうか、" **/Automation**「または」 **-オートメーション**"オプションは、クライアント アプリケーションで、サーバー アプリケーションが起動したかどうかを示します。  
  
```  
BOOL RunAutomated();
```  
  
### <a name="return-value"></a>戻り値  
 オプションが見つかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 存在する場合、オプションはコマンドラインから削除します。 OLE オートメーションの詳細については、記事を参照してください。[オートメーション サーバー](../../mfc/automation-servers.md)します。  
  
##  <a name="runembedded"></a>CWinApp::RunEmbedded  
 判断するには、この関数を呼び出すかどうか、"**埋め込み/**「または」 **-埋め込み**"オプションは、クライアント アプリケーションで、サーバー アプリケーションが起動したかどうかを示します。  
  
```  
BOOL RunEmbedded();
```  
  
### <a name="return-value"></a>戻り値  
 オプションが見つかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 存在する場合、オプションはコマンドラインから削除します。 埋め込みの詳細については、記事を参照してください。[サーバー: サーバーを実装する](../../mfc/servers-implementing-a-server.md)です。  
  
##  <a name="saveallmodified"></a>CWinApp::SaveAllModified  
 アプリケーションのメイン フレーム ウィンドウが閉じられるときにすべてのドキュメントの保存またはにフレームワークによって呼び出され、`WM_QUERYENDSESSION`メッセージです。  
  
```  
virtual BOOL SaveAllModified();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションを終了してもよい場合は 0 以外。アプリケーションを終了する安全でない場合は 0。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の既定の実装、[に対して、順番](../../mfc/reference/cdocument-class.md#savemodified)アプリケーション内のすべての変更されたドキュメントのさらに、メンバー関数。  
  
##  <a name="selectprinter"></a>通知  
 このメンバー関数を呼び出して、特定のプリンターを選択し、[印刷] ダイアログ ボックスで選択されていたプリンターを離します。  
  
```  
void SelectPrinter(
    HANDLE hDevNames,  
    HANDLE hDevMode,  
    BOOL bFreeOld = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `hDevNames`  
 ハンドル、 [DEVNAMES](../../mfc/reference/devnames-structure.md)ドライバー、デバイス、および特定のプリンターの出力ポート名を識別する構造体。  
  
 `hDevMode`  
 ハンドル、 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)をデバイスの初期化とプリンターの環境に関する情報を指定します。  
  
 *bFreeOld*  
 以前に選択されたプリンターを解放します。  
  
### <a name="remarks"></a>コメント  
 両方`hDevMode`と`hDevNames`は**NULL**、`SelectPrinter`現在の既定のプリンターを使用します。  
  
##  <a name="sethelpmode"></a>CWinApp::SetHelpMode  
 アプリケーションのヘルプの種類を設定します。  
  
```  
void SetHelpMode(AFX_HELP_TYPE eHelpType);
```  
  
### <a name="parameters"></a>パラメーター  
 `eHelpType`  
 使用するヘルプの種類を指定します。 参照してください[CWinApp::m_eHelpType](#m_ehelptype)の詳細。  
  
### <a name="remarks"></a>コメント  
 アプリケーションのヘルプの種類を設定します。  
  
 Html ヘルプには、アプリケーションのヘルプの種類を設定を呼び出すことができます[EnableHTMLHelp](#enablehtmlhelp)します。 呼び出す`EnableHTMLHelp`アプリケーションは、ヘルプ アプリケーションとして html ヘルプを使用する必要があります。 WinHelp を使用して変更する場合は、呼び出す`SetHelpMode`設定と`eHelpType`に**afxWinHelp**します。  
  
##  <a name="setregistrykey"></a>書き込むに  
 INI ファイルではなくレジストリに格納されるアプリケーション設定。  
  
```  
void SetRegistryKey(LPCTSTR lpszRegistryKey);  
void SetRegistryKey(UINT nIDRegistryKey);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszRegistryKey*  
 キーの名前を含む文字列へのポインター。  
  
 *nIDRegistryKey*  
 レジストリ キーの名前を含む文字列リソースの ID です。  
  
### <a name="remarks"></a>コメント  
 この関数は設定*m_pszRegistryKey*で使用される、 `GetProfileInt`、 `GetProfileString`、 `WriteProfileInt`、および`WriteProfileString`のメンバー関数`CWinApp`します。 この関数が呼び出された場合、最近使ったファイル (MRU) の一覧は、レジストリにも格納されます。 レジストリ キーは、会社の名前では通常です。 次の形式のキーに格納されている: hkey_current_user\\<company></company>\>\\<application></application>\>\\<section></section>\>\\<value></value>\>します。  
  
##  <a name="supportsapplicationrecovery"></a>CWinApp::SupportsApplicationRecovery  
 再起動マネージャーが予期せず終了したアプリケーションを回復するかどうかを決定します。  
  
```  
virtual BOOL SupportsApplicationRecovery() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`再起動マネージャーの回復には、アプリケーションを示します`FALSE`再起動マネージャーがいないことを示します。  
  
##  <a name="supportsautosaveatinterval"></a>CWinApp::SupportsAutosaveAtInterval  
 再起動マネージャーによって自動保存が一定の間隔でドキュメントを開くかどうかを決定します。  
  
```  
virtual BOOL SupportsAutosaveAtInterval() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`再起動マネージャーによって自動保存がドキュメントを開くことを示します`FALSE`再起動マネージャーがいないことを示します。  
  
##  <a name="supportsautosaveatrestart"></a>CWinApp::SupportsAutosaveAtRestart  
 指定するかどうか再起動マネージャーによって自動保存、アプリケーションの再起動時に、開いているドキュメントです。  
  
```  
virtual BOOL SupportsAutosaveAtRestart() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`アプリケーションが再起動と、再起動マネージャーによって自動保存がドキュメントを開くことを示します`FALSE`再起動マネージャーがいないことを示します。  
  
##  <a name="supportsrestartmanager"></a>CWinApp::SupportsRestartManager  
 アプリケーションが再起動マネージャーをサポートしているかどうかを決定します。  
  
```  
virtual BOOL SupportsRestartManager() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`アプリケーションが再起動マネージャーをサポートしていることを示します。`FALSE`アプリケーションがいないことを示します。  
  
##  <a name="unregister"></a>CWinApp::Unregister  
 アプリケーションのオブジェクトによって登録されたすべてのファイルを登録解除します。  
  
```  
virtual BOOL Unregister();
```  
  
### <a name="return-value"></a>戻り値  
 正常に完了した場合はゼロ以外、それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 `Unregister`関数は、アプリケーションのオブジェクトが実行する登録を元に戻し、[を登録](#register)関数です。 通常は、どちらの関数は MFC によって暗黙的に呼び出され、そのため、コードでは表示されません。  
  
 カスタムの登録解除の手順を実行するには、この関数をオーバーライドします。  
  
##  <a name="unregistershellfiletypes"></a>CWinApp::UnregisterShellFileTypes  
 アプリケーションのドキュメントの種類を Windows ファイル マネージャのすべての登録を解除するには、このメンバー関数を呼び出します。  
  
```  
void UnregisterShellFileTypes();
```  
  
##  <a name="winhelp"></a>Cwinapp::winhelp  
 WinHelp アプリケーションを起動するには、このメンバー関数を呼び出します。  
  
```  
virtual void WinHelp(
    DWORD_PTR dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwData`  
 追加のデータを指定します。 使用される値の値に応じて異なります、`nCmd`パラメーター。  
  
 `nCmd`  
 要求されるヘルプの種類を指定します。 指定できる値とへの影響の一覧については、`dwData`パラメーターを参照してください、 [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267) Windows の機能です。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、WinHelp アプリケーションを起動するには、この関数も呼び出します。  
  
 フレームワークでは、アプリケーションが終了すると、WinHelp アプリケーションは自動的に閉じます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&53;](../../mfc/reference/codesnippet/cpp/cwinapp-class_28.cpp)]  
  
##  <a name="writeprofilebinary"></a>CWinApp::WriteProfileBinary  
 アプリケーションのレジストリの指定されたセクションにバイナリ データを書き込むには、このメンバー関数を呼び出すか。INI ファイルです。  
  
```  
BOOL WriteProfileBinary(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPBYTE pData,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszSection`  
 エントリがあるセクションを指定する NULL で終わる文字列へのポインター。 セクションが存在しない場合は作成されます。 セクションの名前が区別されません。文字列には、任意の大文字と小文字があります。  
  
 `lpszEntry`  
 値が書き込まれるエントリを含む null で終わる文字列へのポインター。 指定されたセクションにエントリが存在しない場合は作成されます。  
  
 `pData`  
 書き込むデータへのポインター。  
  
 `nBytes`  
 書き込むバイト数が含まれています。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 この例では`CWinApp* pApp = AfxGetApp();`方法を示す CWinApp クラスを取得するを`WriteProfileBinary`と`GetProfileBinary`MFC アプリケーションで任意の関数から使用できます。  
  
 [!code-cpp[NVC_MFCWindowing #&54;](../../mfc/reference/codesnippet/cpp/cwinapp-class_29.cpp)]  
  
 別の例の例を参照してください。[は](#getprofilebinary)です。  
  
##  <a name="writeprofileint"></a>Cwinapp::writeprofileint  
 このメンバー関数を呼び出して、指定されたセクションのアプリケーションのレジストリに指定した値を書き込むか。INI ファイルです。  
  
```  
BOOL WriteProfileInt(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    int nValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszSection`  
 エントリがあるセクションを指定する NULL で終わる文字列へのポインター。 セクションが存在しない場合は作成されます。 セクションの名前が区別されません。文字列には、任意の大文字と小文字があります。  
  
 `lpszEntry`  
 値が書き込まれるエントリを含む null で終わる文字列へのポインター。 指定されたセクションにエントリが存在しない場合は作成されます。  
  
 `nValue`  
 書き込まれる値が含まれています。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 この例では`CWinApp* pApp = AfxGetApp();`方法を示す CWinApp クラスを取得するを`WriteProfileString`、 `WriteProfileInt`、 `GetProfileString`、および`GetProfileInt`MFC アプリケーションで任意の関数から使用できます。  
  
 [!code-cpp[NVC_MFCWindowing #&43;](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 別の例の例を参照してください。[は](#getprofileint)です。  
  
##  <a name="writeprofilestring"></a>CWinApp::WriteProfileString  
 このメンバー関数を呼び出して、指定した文字列を指定されたセクションのアプリケーションのレジストリに書き込むか。INI ファイルです。  
  
```  
BOOL WriteProfileString(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszSection`  
 エントリがあるセクションを指定する NULL で終わる文字列へのポインター。 セクションが存在しない場合は作成されます。 セクションの名前が区別されません。文字列には、任意の大文字と小文字があります。  
  
 `lpszEntry`  
 値が書き込まれるエントリを含む null で終わる文字列へのポインター。 指定されたセクションにエントリが存在しない場合は作成されます。 このパラメーターは、する場合`NULL`、指定したセクション`lpszSection`は削除します。  
  
 `lpszValue`  
 書き込む文字列へのポインター。 このパラメーターがある場合`NULL`、指定されたエントリ、`lpszEntry`パラメーターを削除します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&43;](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 別の例の例を参照してください。[は](#getprofileint)です。  
  
##  <a name="setappid"></a>CWinApp::SetAppID  
 アプリケーションのアプリケーションのユーザーのモデル ID を明示的に設定します。 すべてのユーザー インターフェイスを (最適な場所は、アプリケーションのコンス トラクターは) ユーザーに表示する前に、このメソッドを呼び出す必要があります。  
  
```  
void SetAppID(LPCTSTR lpcszAppID);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpcszAppID`  
 アプリケーション ユーザーのモデル ID を指定します  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [CWinThread クラス](../../mfc/reference/cwinthread-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [方法: 再起動マネージャーのサポートを追加](../../mfc/how-to-add-restart-manager-support.md)




