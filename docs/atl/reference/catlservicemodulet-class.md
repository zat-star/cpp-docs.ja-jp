---
title: "CAtlServiceModuleT クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT::CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT::Handler
- ATLBASE/ATL::CAtlServiceModuleT::InitializeSecurity
- ATLBASE/ATL::CAtlServiceModuleT::Install
- ATLBASE/ATL::CAtlServiceModuleT::IsInstalled
- ATLBASE/ATL::CAtlServiceModuleT::LogEvent
- ATLBASE/ATL::CAtlServiceModuleT::OnContinue
- ATLBASE/ATL::CAtlServiceModuleT::OnInterrogate
- ATLBASE/ATL::CAtlServiceModuleT::OnPause
- ATLBASE/ATL::CAtlServiceModuleT::OnShutdown
- ATLBASE/ATL::CAtlServiceModuleT::OnStop
- ATLBASE/ATL::CAtlServiceModuleT::OnUnknownRequest
- ATLBASE/ATL::CAtlServiceModuleT::ParseCommandLine
- ATLBASE/ATL::CAtlServiceModuleT::PreMessageLoop
- ATLBASE/ATL::CAtlServiceModuleT::RegisterAppId
- ATLBASE/ATL::CAtlServiceModuleT::Run
- ATLBASE/ATL::CAtlServiceModuleT::ServiceMain
- ATLBASE/ATL::CAtlServiceModuleT::SetServiceStatus
- ATLBASE/ATL::CAtlServiceModuleT::Start
- ATLBASE/ATL::CAtlServiceModuleT::Uninstall
- ATLBASE/ATL::CAtlServiceModuleT::Unlock
- ATLBASE/ATL::CAtlServiceModuleT::UnregisterAppId
- ATLBASE/ATL::CAtlServiceModuleT::WinMain
- ATLBASE/ATL::CAtlServiceModuleT::m_bService
- ATLBASE/ATL::CAtlServiceModuleT::m_dwThreadID
- ATLBASE/ATL::CAtlServiceModuleT::m_hServiceStatus
- ATLBASE/ATL::CAtlServiceModuleT::m_status
- ATLBASE/ATL::CAtlServiceModuleT::m_szServiceName
dev_langs:
- C++
helpviewer_keywords:
- CAtlServiceModuleT class
ms.assetid: 8fc753ce-4a50-402b-9b4a-0a4ce5dd496c
caps.latest.revision: 20
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
ms.openlocfilehash: c8fcadca667b618d9e5f112d7910c8e6e6f6c65d
ms.lasthandoff: 02/24/2017

---
# <a name="catlservicemodulet-class"></a>CAtlServiceModuleT クラス
このクラスは、サービスを実装します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T, UINT nServiceNameID>  
class ATL_NO_VTABLE CAtlServiceModuleT : public CAtlExeModuleT<T>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス`CAtlServiceModuleT`します。  
  
 *nServiceNameID*  
 サービスのリソースの識別子です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlServiceModuleT::CAtlServiceModuleT](#catlservicemodulet)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlServiceModuleT::Handler](#handler)|サービスのハンドラー ルーチンです。|  
|[CAtlServiceModuleT::InitializeSecurity](#initializesecurity)|既定値に、サービスのセキュリティ設定を提供します。|  
|[CAtlServiceModuleT::Install](#install)|インストールし、サービスを作成します。|  
|[CAtlServiceModuleT::IsInstalled](#isinstalled)|サービスがインストールされていることを確認します。|  
|[CAtlServiceModuleT::LogEvent](#logevent)|イベント ログに書き込みます。|  
|[CAtlServiceModuleT::OnContinue](#oncontinue)|サービスを続行するには、このメソッドをオーバーライドします。|  
|[CAtlServiceModuleT::OnInterrogate](#oninterrogate)|サービスを調査するには、このメソッドをオーバーライドします。|  
|[CAtlServiceModuleT::OnPause](#onpause)|サービスを一時停止するには、このメソッドをオーバーライドします。|  
|[CAtlServiceModuleT::OnShutdown](#onshutdown)|サービスを停止するには、このメソッドをオーバーライドします。|  
|[CAtlServiceModuleT::OnStop](#onstop)|サービスを停止するには、このメソッドをオーバーライドします。|  
|[されない](#onunknownrequest)|サービスに不明な要求を処理するには、このメソッドをオーバーライドします。|  
|[CAtlServiceModuleT::ParseCommandLine](#parsecommandline)|コマンドラインを解析し、必要な場合は、登録を実行します。|  
|[CAtlServiceModuleT::PreMessageLoop](#premessageloop)|このメソッドは、メッセージ ループに入る前にすぐに呼び出されます。|  
|[CAtlServiceModuleT::RegisterAppId](#registerappid)|レジストリにサービスを登録します。|  
|[主要な](#run)|サービスを実行します。|  
|[CAtlServiceModuleT::ServiceMain](#servicemain)|サービス コントロール マネージャーから呼び出されるメソッド。|  
|[CAtlServiceModuleT::SetServiceStatus](#setservicestatus)|サービスの状態を更新します。|  
|[CAtlServiceModuleT::Start](#start)|によって呼び出される`CAtlServiceModuleT::WinMain`サービスの起動時にします。|  
|[CAtlServiceModuleT::Uninstall](#uninstall)|停止し、サービスを削除します。|  
|[CAtlServiceModuleT::Unlock](#unlock)|サービスのロック カウントをデクリメントします。|  
|[CAtlServiceModuleT::UnregisterAppId](#unregisterappid)|レジストリからサービスを削除します。|  
|[起動時](#winmain)|このメソッドでは、サービスの実行に必要なコードを実装します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlServiceModuleT::m_bService](#m_bservice)|サービスとして実行中のプログラムを示すフラグします。|  
|[CAtlServiceModuleT::m_dwThreadID](#m_dwthreadid)|スレッド識別子を格納するメンバー変数です。|  
|[CAtlServiceModuleT::m_hServiceStatus](#m_hservicestatus)|現在のサービスのステータス情報の構造体へのハンドルを格納するメンバー変数です。|  
|[CAtlServiceModuleT::m_status](#m_status)|現在のサービスのステータス情報の構造体を格納するメンバー変数です。|  
|[CAtlServiceModuleT::m_szServiceName](#m_szservicename)|登録されているサービスの名前。|  
  
## <a name="remarks"></a>コメント  
 `CAtlServiceModuleT`、から派生した[CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)、ATL サービス モジュールを実装します。 `CAtlServiceModuleT`コマンドライン処理、インストール、登録、および削除のメソッドを提供します。 追加の機能が必要な場合は、これらおよびその他のメソッドがオーバーライドできます。  
  
 このクラスは廃止された置換[CComModule クラス](../../atl/reference/ccommodule-class.md)ATL の以前のバージョンで使用されます。 参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [不要](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)  
  
 `CAtlServiceModuleT`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="catlservicemodulet"></a>CAtlServiceModuleT::CAtlServiceModuleT  
 コンストラクターです。  
  
```
CAtlServiceModuleT() throw();
```  
  
### <a name="remarks"></a>コメント  
 データ メンバーを初期化し、最初のサービスの状態を設定します。  
  
##  <a name="handler"></a>CAtlServiceModuleT::Handler  
 サービスのハンドラー ルーチンです。  
  
```
void Handler(DWORD dwOpcode) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *dwOpcode*  
 ハンドラーの操作を定義するスイッチです。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 これは、サービス コントロール マネージャー (SCM) は、停止などのサービスと問題の手順の状態を取得または一時停止を呼び出すコードです。 SCM は、次に、操作コードを渡します`Handler`をすれば、サービスを示します。  
  
|操作コード|説明|  
|--------------------|-------------|  
|SERVICE_CONTROL_STOP|サービスを停止します。 メソッドをオーバーライドする[CAtlServiceModuleT::OnStop](#onstop) atlbase.h 動作を変更するのです。|  
|SERVICE_CONTROL_PAUSE|ユーザーが実装されています。 空のメソッドをオーバーライドして[CAtlServiceModuleT::OnPause](#onpause) atlbase.h サービスを一時停止にします。|  
|SERVICE_CONTROL_CONTINUE|ユーザーが実装されています。 空のメソッドをオーバーライドして[CAtlServiceModuleT::OnContinue](#oncontinue) atlbase.h、サービスを続行するのです。|  
|SERVICE_CONTROL_INTERROGATE|ユーザーが実装されています。 空のメソッドをオーバーライドして[CAtlServiceModuleT::OnInterrogate](#oninterrogate) atlbase.h、サービスを調査するのです。|  
|SERVICE_CONTROL_SHUTDOWN|ユーザーが実装されています。 空のメソッドをオーバーライドして[CAtlServiceModuleT::OnShutdown](#onshutdown) atlbase.h サービスをシャット ダウンするのです。|  
  
 操作コードが認識されない場合、メソッド[されない](#onunknownrequest)が呼び出されます。  
  
 既定の ATL によって生成されたサービスは、stop 命令を処理するのみです。 SCM では、stop 命令が成功した場合、サービスは、プログラムを停止するが、SCM を指示します。 サービスが、呼び出す`PostThreadMessage`自体に終了メッセージを投稿します。 メッセージ ループが終了し、サービスが最終的に終了します。  
  
##  <a name="initializesecurity"></a>CAtlServiceModuleT::InitializeSecurity  
 既定値に、サービスのセキュリティ設定を提供します。  
  
```
HRESULT InitializeSecurity() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 Visual Studio .NET 2003 では、このメソッドは、基底クラスで実装されていません。 Visual Studio プロジェクト ウィザードには、生成されたコードにこのメソッドが含まれていますが、Visual C の以前のバージョンで作成したプロジェクトをコンパイルした ATL 7.1 を使用する場合、コンパイル エラーが発生します。 任意のクラスから派生した`CAtlServiceModuleT`派生クラスでこのメソッドを実装する必要があります。  
  
 呼び出しで PKT レベルの認証、RPC_C_IMP_LEVEL_IDENTIFY の偽装レベルおよび適切な null 以外のセキュリティ記述子を使用して**CoInitializeSecurity**します。  
  
 属性なしのサービスをウィザードで生成されたプロジェクトでは、次のようになります。  
  
 [!code-cpp[NVC_ATL_Service&#1;](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_1.cpp)]  
  
 属性サービス プロジェクトでは、次のようになります。  
  
 [!code-cpp[NVC_ATL_ServiceAttrib&#1;](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_2.cpp)]  
  
##  <a name="install"></a>CAtlServiceModuleT::Install  
 インストールし、サービスを作成します。  
  
```
BOOL Install() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
### <a name="remarks"></a>コメント  
 サービス コントロール マネージャー (SCM) データベースにサービスをインストールし、サービス オブジェクトを作成します。 サービスを作成しない場合は、メッセージ ボックスが表示され、FALSE を返します。  
  
##  <a name="isinstalled"></a>CAtlServiceModuleT::IsInstalled  
 サービスがインストールされていることを確認します。  
  
```
BOOL IsInstalled() throw();
```  
  
### <a name="return-value"></a>戻り値  
 サービスがインストールされているそれ以外の場合は TRUE を返します。  
  
##  <a name="logevent"></a>CAtlServiceModuleT::LogEvent  
 イベント ログに書き込みます。  
  
```
void __cdecl LogEvent(LPCTSTR pszFormat, ...) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszFormat`  
 イベント ログに書き込む文字列。  
  
 ...  
 イベント ログに書き込まれる省略可能な余分な文字列です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、の詳細を関数を使用して、イベント ログに書き込みます[ReportEvent](http://msdn.microsoft.com/library/windows/desktop/aa363679)します。 サービスが実行されていない場合、文字列がコンソールに送信されます。  
  
##  <a name="m_bservice"></a>CAtlServiceModuleT::m_bService  
 サービスとして実行中のプログラムを示すフラグします。  
  
```
BOOL m_bService;
```  
  
### <a name="remarks"></a>コメント  
 アプリケーションの exe ファイルからサービス EXE を区別するために使用されます。  
  
##  <a name="m_dwthreadid"></a>CAtlServiceModuleT::m_dwThreadID  
 サービスのスレッド識別子を格納するメンバー変数です。  
  
```
DWORD m_dwThreadID;
```  
  
### <a name="remarks"></a>コメント  
 この変数は、現在のスレッドのスレッド識別子を格納します。  
  
##  <a name="m_hservicestatus"></a>CAtlServiceModuleT::m_hServiceStatus  
 現在のサービスのステータス情報の構造体へのハンドルを格納するメンバー変数です。  
  
```
SERVICE_STATUS_HANDLE m_hServiceStatus;
```  
  
### <a name="remarks"></a>コメント  
 [SERVICE_STATUS](http://msdn.microsoft.com/library/windows/desktop/ms685996)構造体には、サービスに関する情報が含まれています。  
  
##  <a name="m_status"></a>CAtlServiceModuleT::m_status  
 現在のサービスのステータス情報の構造体を格納するメンバー変数です。  
  
```
SERVICE_STATUS m_status;
```  
  
### <a name="remarks"></a>コメント  
 [SERVICE_STATUS](http://msdn.microsoft.com/library/windows/desktop/ms685996)構造体には、サービスに関する情報が含まれています。  
  
##  <a name="m_szservicename"></a>CAtlServiceModuleT::m_szServiceName  
 登録されているサービスの名前。  
  
```
TCHAR [256] m_szServiceName;
```  
  
### <a name="remarks"></a>コメント  
 サービスの名前を格納する null で終わる文字列。  
  
##  <a name="oncontinue"></a>CAtlServiceModuleT::OnContinue  
 サービスを続行するには、このメソッドをオーバーライドします。  
  
```
void OnContinue() throw();
```  
  
##  <a name="oninterrogate"></a>CAtlServiceModuleT::OnInterrogate  
 サービスを調査するには、このメソッドをオーバーライドします。  
  
```
void OnInterrogate() throw();
```  
  
##  <a name="onpause"></a>CAtlServiceModuleT::OnPause  
 サービスを一時停止するには、このメソッドをオーバーライドします。  
  
```
void OnPause() throw();
```  
  
##  <a name="onshutdown"></a>CAtlServiceModuleT::OnShutdown  
 サービスを停止するには、このメソッドをオーバーライドします。  
  
```
void OnShutdown() throw();
```  
  
##  <a name="onstop"></a>CAtlServiceModuleT::OnStop  
 サービスを停止するには、このメソッドをオーバーライドします。  
  
```
void OnStop() throw();
```  
  
##  <a name="onunknownrequest"></a>されない  
 サービスに不明な要求を処理するには、このメソッドをオーバーライドします。  
  
```
void OnUnknownRequest(DWORD /* dwOpcode*/) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 */\*dwOpcode\*/*  
 予約済み。  
  
##  <a name="parsecommandline"></a>CAtlServiceModuleT::ParseCommandLine  
 コマンドラインを解析し、必要な場合は、登録を実行します。  
  
```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpCmdLine`  
 コマンド ライン。  
  
 `pnRetCode`  
 (場所がかかりました) 場合は、登録に対応する HRESULT。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、またはコマンドラインで指定された RG ファイルを登録されていない場合は false、true を返します。  
  
### <a name="remarks"></a>コメント  
 コマンドラインを解析して登録するか必要な場合は、指定された RG ファイルの登録を解除します。 このメソッドを呼び出す[CAtlExeModuleT::ParseCommandLine](../../atl/reference/catlexemodulet-class.md#parsecommandline)をチェックする**/RegServer**と**/UnregServer**します。 引数を追加する**-/service**サービスを登録します。  
  
##  <a name="premessageloop"></a>CAtlServiceModuleT::PreMessageLoop  
 このメソッドは、メッセージ ループに入る前にすぐに呼び出されます。  
  
```
HRESULT PreMessageLoop(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nShowCmd`  
 このパラメーターに渡された[CAtlExeModuleT::PreMessageLoop](../../atl/reference/catlexemodulet-class.md#premessageloop)します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 サービスのカスタムの初期化コードを追加するには、このメソッドをオーバーライドします。  
  
##  <a name="registerappid"></a>CAtlServiceModuleT::RegisterAppId  
 レジストリにサービスを登録します。  
  
```
inline HRESULT RegisterAppId(bool bService = false) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *bService*  
 サービスとして登録する場合は true にする必要があります。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="run"></a>主要な  
 サービスを実行します。  
  
```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nShowCmd`  
 ウィンドウの表示方法を指定します。 このパラメーターには、「値のいずれかを指定できます、 [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559)セクションです。 既定値は、SW_HIDE です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出された後に**実行**呼び出し[CAtlServiceModuleT::PreMessageLoop](#premessageloop)、 [CAtlExeModuleT::RunMessageLoop](../../atl/reference/catlexemodulet-class.md#runmessageloop)、および[CAtlExeModuleT::PostMessageLoop](../../atl/reference/catlexemodulet-class.md#postmessageloop)します。  
  
##  <a name="servicemain"></a>CAtlServiceModuleT::ServiceMain  
 サービス コントロール マネージャーから呼び出されます。  
  
```
void ServiceMain(DWORD dwArgc, LPTSTR* lpszArgv) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *dwArgc*  
 Argc 引数です。  
  
 *lpszArgv*  
 Argv 引数です。  
  
### <a name="remarks"></a>コメント  
 サービス コントロール マネージャー (SCM) 呼び出し`ServiceMain`コントロール パネルの サービス アプリケーションを開くと、サービスを選択し、開始 をクリックします。  
  
 SCM 後を呼び出して`ServiceMain`サービスがハンドラー関数には、SCM の提供する必要があります。 この関数では、SCM はサービスの状態を取得して (一時停止または停止) などの具体的な手順を渡すことができます。 その後、[主要な](#run)を呼び出して、サービスの主要な処理を実行します。 **実行**サービスが停止されるまでの実行を継続します。  
  
##  <a name="setservicestatus"></a>CAtlServiceModuleT::SetServiceStatus  
 このメソッドは、サービスの状態を更新します。  
  
```
void SetServiceStatus(DWORD dwState) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dwState`  
 新しいステータス。 参照してください[SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241)使用可能な値にします。  
  
### <a name="remarks"></a>コメント  
 サービスのサービス コントロール マネージャーのステータス情報を更新します。 によって呼び出される[主要な](#run)、 [CAtlServiceModuleT::ServiceMain](#servicemain)およびその他のハンドラー メソッド。 状態は、メンバー変数にも格納[CAtlServiceModuleT::m_status](#m_status)します。  
  
##  <a name="start"></a>CAtlServiceModuleT::Start  
 によって呼び出される`CAtlServiceModuleT::WinMain`サービスの起動時にします。  
  
```
HRESULT Start(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nShowCmd`  
 ウィンドウの表示方法を指定します。 このパラメーターには、「値のいずれかを指定できます、 [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559)セクションです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 [起動時](#winmain)メソッド登録とインストールの両方を処理するだけでなくタスクのレジストリ エントリを削除して、モジュールのアンインストールに関与します。 サービスの実行時に`WinMain`呼び出し**開始**します。  
  
##  <a name="uninstall"></a>CAtlServiceModuleT::Uninstall  
 停止し、サービスを削除します。  
  
```
BOOL Uninstall() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
### <a name="remarks"></a>コメント  
 実行中のサービスを停止し、サービス コントロール マネージャーのデータベースから削除します。  
  
##  <a name="unlock"></a>CAtlServiceModuleT::Unlock  
 サービスのロック カウントをデクリメントします。  
  
```
LONG Unlock() throw();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役立ちますをデバッグすることもロック カウントを返します。  
  
##  <a name="unregisterappid"></a>CAtlServiceModuleT::UnregisterAppId  
 レジストリからサービスを削除します。  
  
```
HRESULT UnregisterAppId() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="winmain"></a>起動時  
 このメソッドでは、サービスを開始するために必要なコードを実装します。  
  
```
int WinMain(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nShowCmd`  
 ウィンドウの表示方法を指定します。 このパラメーターには、「値のいずれかを指定できます、 [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559)セクションです。  
  
### <a name="return-value"></a>戻り値  
 サービスの戻り値を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、コマンド ラインを処理 (と[CAtlServiceModuleT::ParseCommandLine](#parsecommandline)) と、サービスが開始されます (を使用して[CAtlServiceModuleT::Start](#start))。  
  
## <a name="see-also"></a>関連項目  
 [CAtlExeModuleT クラス](../../atl/reference/catlexemodulet-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

