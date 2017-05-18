---
title: "CAccessToken クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAccessToken
- ATLSECURITY/ATL::CAccessToken
- ATLSECURITY/ATL::CAccessToken::Attach
- ATLSECURITY/ATL::CAccessToken::CheckTokenMembership
- ATLSECURITY/ATL::CAccessToken::CreateImpersonationToken
- ATLSECURITY/ATL::CAccessToken::CreatePrimaryToken
- ATLSECURITY/ATL::CAccessToken::CreateProcessAsUser
- ATLSECURITY/ATL::CAccessToken::CreateRestrictedToken
- ATLSECURITY/ATL::CAccessToken::Detach
- ATLSECURITY/ATL::CAccessToken::DisablePrivilege
- ATLSECURITY/ATL::CAccessToken::DisablePrivileges
- ATLSECURITY/ATL::CAccessToken::EnablePrivilege
- ATLSECURITY/ATL::CAccessToken::EnablePrivileges
- ATLSECURITY/ATL::CAccessToken::GetDefaultDacl
- ATLSECURITY/ATL::CAccessToken::GetEffectiveToken
- ATLSECURITY/ATL::CAccessToken::GetGroups
- ATLSECURITY/ATL::CAccessToken::GetHandle
- ATLSECURITY/ATL::CAccessToken::GetImpersonationLevel
- ATLSECURITY/ATL::CAccessToken::GetLogonSessionId
- ATLSECURITY/ATL::CAccessToken::GetLogonSid
- ATLSECURITY/ATL::CAccessToken::GetOwner
- ATLSECURITY/ATL::CAccessToken::GetPrimaryGroup
- ATLSECURITY/ATL::CAccessToken::GetPrivileges
- ATLSECURITY/ATL::CAccessToken::GetProcessToken
- ATLSECURITY/ATL::CAccessToken::GetProfile
- ATLSECURITY/ATL::CAccessToken::GetSource
- ATLSECURITY/ATL::CAccessToken::GetStatistics
- ATLSECURITY/ATL::CAccessToken::GetTerminalServicesSessionId
- ATLSECURITY/ATL::CAccessToken::GetThreadToken
- ATLSECURITY/ATL::CAccessToken::GetTokenId
- ATLSECURITY/ATL::CAccessToken::GetType
- ATLSECURITY/ATL::CAccessToken::GetUser
- ATLSECURITY/ATL::CAccessToken::HKeyCurrentUser
- ATLSECURITY/ATL::CAccessToken::Impersonate
- ATLSECURITY/ATL::CAccessToken::ImpersonateLoggedOnUser
- ATLSECURITY/ATL::CAccessToken::IsTokenRestricted
- ATLSECURITY/ATL::CAccessToken::LoadUserProfile
- ATLSECURITY/ATL::CAccessToken::LogonUser
- ATLSECURITY/ATL::CAccessToken::OpenCOMClientToken
- ATLSECURITY/ATL::CAccessToken::OpenNamedPipeClientToken
- ATLSECURITY/ATL::CAccessToken::OpenRPCClientToken
- ATLSECURITY/ATL::CAccessToken::OpenThreadToken
- ATLSECURITY/ATL::CAccessToken::PrivilegeCheck
- ATLSECURITY/ATL::CAccessToken::Revert
- ATLSECURITY/ATL::CAccessToken::SetDefaultDacl
- ATLSECURITY/ATL::CAccessToken::SetOwner
- ATLSECURITY/ATL::CAccessToken::SetPrimaryGroup
dev_langs:
- C++
helpviewer_keywords:
- CAccessToken class
ms.assetid: bb5c5945-56a5-4083-b442-76573cee83ab
caps.latest.revision: 24
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 79845a2be4f79a1ee94a9440e8508bcb0e38bcdd
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="caccesstoken-class"></a>CAccessToken クラス
このクラスは、アクセス トークンのラッパーです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CAccessToken
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAccessToken:: ~ CAccessToken](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAccessToken::Attach](#attach)|指定されたアクセス トークンのハンドルの所有権を取得するには、このメソッドを呼び出します。|  
|[CAccessToken::CheckTokenMembership](#checktokenmembership)|指定された SID が有効になっているかどうかを判断するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。|  
|[CAccessToken::CreateImpersonationToken](#createimpersonationtoken)|新しい偽装アクセス トークンを作成するには、このメソッドを呼び出します。|  
|[CAccessToken::CreatePrimaryToken](#createprimarytoken)|新しいプライマリ トークンを作成するには、このメソッドを呼び出します。|  
|[CAccessToken::CreateProcessAsUser](#createprocessasuser)|によって表されるユーザーのセキュリティ コンテキストで実行されている新しいプロセスを作成するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。|  
|[CAccessToken::CreateRestrictedToken](#createrestrictedtoken)|を新規作成するのには、このメソッドを呼び出す制限`CAccessToken`オブジェクトです。|  
|[CAccessToken::Detach](#detach)|このメソッドを呼び出してアクセス トークンの所有権を放棄します。|  
|[CAccessToken::DisablePrivilege](#disableprivilege)|権限を無効にするには、このメソッドを呼び出す、`CAccessToken`オブジェクトです。|  
|[CAccessToken::DisablePrivileges](#disableprivileges)|1 つ以上の特権を無効にするには、このメソッドを呼び出す、`CAccessToken`オブジェクトです。|  
|[CAccessToken::EnablePrivilege](#enableprivilege)|特権を有効にするには、このメソッドを呼び出す、`CAccessToken`オブジェクトです。|  
|[CAccessToken::EnablePrivileges](#enableprivileges)|1 つ以上の特権を有効にするには、このメソッドを呼び出す、`CAccessToken`オブジェクトです。|  
|[CAccessToken::GetDefaultDacl](#getdefaultdacl)|返すには、このメソッドを呼び出して、`CAccessToken`オブジェクトの DACL を既定値です。|  
|[CAccessToken::GetEffectiveToken](#geteffectivetoken)|このメソッドを呼び出して取得、`CAccessToken`現在のスレッドに対して有効アクセス トークンと等しいオブジェクト。|  
|[CAccessToken::GetGroups](#getgroups)|返すには、このメソッドを呼び出して、`CAccessToken`トークンのオブジェクトのグループです。|  
|[CAccessToken::GetHandle](#gethandle)|アクセス トークンを識別するハンドルを取得するには、このメソッドを呼び出します。|  
|[CAccessToken::GetImpersonationLevel](#getimpersonationlevel)|アクセス トークンから偽装レベルを取得するには、このメソッドを呼び出します。|  
|[CAccessToken::GetLogonSessionId](#getlogonsessionid)|関連付けられているログオン セッション ID を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。|  
|[CAccessToken::GetLogonSid](#getlogonsid)|関連付けられているログオン SID を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。|  
|[CAccessToken::GetOwner](#getowner)|関連付けられている所有者を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。|  
|[CAccessToken::GetPrimaryGroup](#getprimarygroup)|関連付けられているプライマリ グループを取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。|  
|[CAccessToken::GetPrivileges](#getprivileges)|関連付けられている権限を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。|  
|[CAccessToken::GetProcessToken](#getprocesstoken)|指定されたプロセスからアクセス トークンを使用して `CAccessToken` を初期化するには、このメソッドを呼び出します。|  
|[CAccessToken::GetProfile](#getprofile)|関連付けられたユーザー プロファイルを指すハンドルを取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。|  
|[CAccessToken::GetSource](#getsource)|ソースを取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。|  
|[CAccessToken::GetStatistics](#getstatistics)|関連付けられている情報を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。|  
|[CAccessToken::GetTerminalServicesSessionId](#getterminalservicessessionid)|関連付けられているターミナル サービス セッションの ID を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。|  
|[CAccessToken::GetThreadToken](#getthreadtoken)|初期化するには、このメソッドを呼び出して、`CAccessToken`特定のスレッドからのトークンに置き換えます。|  
|[CAccessToken::GetTokenId](#gettokenid)|関連付けられているトークンの ID を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。|  
|[CAccessToken::GetType](#gettype)|トークンの種類を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。|  
|[CAccessToken::GetUser](#getuser)|関連付けられているユーザーを識別するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。|  
|[CAccessToken::HKeyCurrentUser](#hkeycurrentuser)|関連付けられたユーザー プロファイルを指すハンドルを取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。|  
|[CAccessToken::Impersonate](#impersonate)|権限の借用を割り当てるには、このメソッドを呼び出す`CAccessToken`スレッドにします。|  
|[CAccessToken::ImpersonateLoggedOnUser](#impersonateloggedonuser)|呼び出し元スレッドでは、ログオン ユーザーのセキュリティ コンテキストを偽装を許可するようにこのメソッドを呼び出します。|  
|[CAccessToken::IsTokenRestricted](#istokenrestricted)|場合にテストするには、このメソッドを呼び出して、`CAccessToken`オブジェクトには、制限付き Sid の一覧が含まれています。|  
|[CAccessToken::LoadUserProfile](#loaduserprofile)|このメソッドに関連付けられているユーザー プロファイルの読み込みを呼び出して、`CAccessToken`オブジェクトです。|  
|[CAccessToken::LogonUser](#logonuser)|指定した資格情報に関連付けられているユーザーのログオン セッションを作成するには、このメソッドを呼び出します。|  
|[CAccessToken::OpenCOMClientToken](#opencomclienttoken)|初期化するために、クライアントからの呼び出しを処理する COM サーバー内からこのメソッドを呼び出して、 `CAccessToken` COM クライアントからアクセス トークンを使用します。|  
|[CAccessToken::OpenNamedPipeClientToken](#opennamedpipeclienttoken)|初期化するために名前付きパイプ経由でこのメソッドは、サーバー内から作成要求を呼び出す、`CAccessToken`クライアントからアクセス トークンを使用します。|  
|[CAccessToken::OpenRPCClientToken](#openrpcclienttoken)|初期化するには、RPC クライアントから呼び出しを処理するサーバー内からこのメソッドを呼び出して、`CAccessToken`クライアントからアクセス トークンを使用します。|  
|[CAccessToken::OpenThreadToken](#openthreadtoken)|偽装レベルを設定し、初期化するには、このメソッドを呼び出して、`CAccessToken`特定のスレッドからのトークンに置き換えます。|  
|[CAccessToken::PrivilegeCheck](#privilegecheck)|指定された権限のセットが有効にするかどうかを判断するには、このメソッドを呼び出して、 **CAccessToken**オブジェクトです。|  
|[CAccessToken::Revert](#revert)|権限借用トークンを使用しているスレッドを停止するには、このメソッドを呼び出します。|  
|[CAccessToken::SetDefaultDacl](#setdefaultdacl)|既定値を設定するには、このメソッドを呼び出すの DACL、`CAccessToken`オブジェクトです。|  
|[CAccessToken::SetOwner](#setowner)|所有者を設定するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。|  
|[CAccessToken::SetPrimaryGroup](#setprimarygroup)|プライマリ グループを設定するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 [アクセス トークン](http://msdn.microsoft.com/library/windows/desktop/aa374909)プロセスまたはスレッドのセキュリティ コンテキストについて説明し、Windows NT または Windows 2000 のシステムにログオンしている各ユーザーに割り当てられているオブジェクトです。  
  
 Windows のアクセス制御モデルの概要については、次を参照してください。[アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h  
  
##  <a name="attach"></a>CAccessToken::Attach  
 指定されたアクセス トークンのハンドルの所有権を取得するには、このメソッドを呼び出します。  
  
```
void Attach(HANDLE hToken) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *hToken*  
 アクセス トークンへのハンドル。  
  
### <a name="remarks"></a>コメント  
 場合はデバッグ ビルドで、アサーション エラーが発生、`CAccessToken`オブジェクトにはアクセス トークンの所有権が既に存在します。  
  
##  <a name="dtor"></a>CAccessToken:: ~ CAccessToken  
 デストラクターです。  
  
```
virtual ~CAccessToken() throw();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放します。  
  
##  <a name="checktokenmembership"></a>CAccessToken::CheckTokenMembership  
 指定された SID が有効になっているかどうかを判断するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。  
  
```
bool CheckTokenMembership(
    const CSid& rSid, 
    bool* pbIsMember) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rSid`  
 参照、 [CSid クラス](../../atl/reference/csid-class.md)オブジェクトです。  
  
 `pbIsMember`  
 チェックの結果を受け取る変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 `CheckTokenMembership`メソッドでは、ユーザーとアクセス トークンのグループの Sid、SID の存在を確認します。 SID が存在し、SE_GROUP_ENABLED 属性を持つ場合*pbIsMember*には true、それ以外の場合を設定するには、false に設定されています。  
  
 デバッグ ビルドで、アサーション エラーが発生場合`pbIsMember`が有効なポインターでないです。  
  
> [!NOTE]
>  `CAccessToken`偽装トークンとプライマリのトークンではないオブジェクトがある必要があります。  
  
##  <a name="createimpersonationtoken"></a>CAccessToken::CreateImpersonationToken  
 偽装アクセス トークンを作成するには、このメソッドを呼び出します。  
  
```
bool CreateImpersonationToken(
    CAccessToken* pImp, 
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pImp`  
 新しいポインター`CAccessToken`オブジェクトです。  
  
 `sil`  
 指定する[SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572)新しいトークンの偽装レベルを提供する型を列挙します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 `CreateImpersonationToken`呼び出し[DuplicateToken](http://msdn.microsoft.com/library/windows/desktop/aa446616)新しい権限借用トークンを作成します。  
  
##  <a name="createprimarytoken"></a>CAccessToken::CreatePrimaryToken  
 新しいプライマリ トークンを作成するには、このメソッドを呼び出します。  
  
```
bool CreatePrimaryToken(
    CAccessToken* pPri,
    DWORD dwDesiredAccess = MAXIMUM_ALLOWED,
    const CSecurityAttributes* pTokenAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *pPri*  
 新しいポインター`CAccessToken`オブジェクトです。  
  
 `dwDesiredAccess`  
 新しいトークンの要求されたアクセス権を指定します。 MAXIMUM_ALLOWED、既定値は、呼び出し元に対して有効なすべてのアクセス権を要求します。 参照してください[アクセス権とアクセス マスク](http://msdn.microsoft.com/library/windows/desktop/aa374902)のアクセス権の詳細にします。  
  
 *pTokenAttributes*  
 ポインター、 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)構造体を新しいトークンのセキュリティ記述子を指定し、子プロセスがトークンを継承するかどうかを決定します。 場合*pTokenAttributes* null、トークンは、既定のセキュリティ記述子を取得し、ハンドルは継承できません。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 `CreatePrimaryToken`呼び出し[DuplicateTokenEx](http://msdn.microsoft.com/library/windows/desktop/aa446617)を新しいプライマリ トークンを作成します。  
  
##  <a name="createprocessasuser"></a>CAccessToken::CreateProcessAsUser  
 によって表されるユーザーのセキュリティ コンテキストで実行されている新しいプロセスを作成するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。  
  
```
bool CreateProcessAsUser(
    LPCTSTR pApplicationName,
    LPTSTR pCommandLine,
    LPPROCESS_INFORMATION pProcessInformation,
    LPSTARTUPINFO pStartupInfo,
    DWORD dwCreationFlags = NORMAL_PRIORITY_CLASS,
    bool bLoadProfile = false,
    const CSecurityAttributes* pProcessAttributes = NULL,
    const CSecurityAttributes* pThreadAttributes = NULL,
    bool bInherit = false,
    LPCTSTR pCurrentDirectory = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pApplicationName*  
 実行するモジュールを指定する null で終わる文字列へのポインター。 このパラメーターには、NULL はでもかまいません。  
  
 *pCommandLine*  
 実行するコマンドラインを指定する null で終わる文字列へのポインター。  
  
 *pProcessInformation*  
 ポインター、[ハンドル](http://msdn.microsoft.com/library/windows/desktop/ms684873)を新しいプロセスの識別情報を受け取る構造体。  
  
 *pStartupInfo*  
 ポインター、 [STARTUPINFO](http://msdn.microsoft.com/library/windows/desktop/ms686331)を新しいプロセスのメイン ウィンドウの表示方法を指定します。  
  
 `dwCreationFlags`  
 優先順位クラスとプロセスの作成を制御する追加のフラグを指定します。 Win32 関数を参照して[CreateProcessAsUser](http://msdn.microsoft.com/library/windows/desktop/ms682429)フラグの一覧にします。  
  
 *bLoadProfile*  
 True のかどうか、ユーザーのプロファイルがで読み込まれます[LoadUserProfile](http://msdn.microsoft.com/library/windows/desktop/bb762281)します。  
  
 *pProcessAttributes*  
 ポインター、 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)構造体を新しいプロセスのセキュリティ記述子を指定し、返されたハンドルを子プロセスが継承するかどうかを決定します。 場合*pProcessAttributes* null、プロセスは、既定のセキュリティ記述子を取得し、ハンドルは継承できません。  
  
 *pThreadAttributes*  
 ポインター、 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)構造を新しいスレッドのセキュリティ記述子を指定し、返されたハンドルを子プロセスが継承するかどうかを決定します。 場合*pThreadAttributes* null、スレッドは、既定のセキュリティ記述子を取得し、ハンドルは継承できません。  
  
 *bInherit*  
 新しいプロセスが呼び出しプロセスからハンドルを継承するかどうかを示します。 True の場合、呼び出し元のプロセス内の継承可能な各開いているハンドルは、新しいプロセスによって継承されます。 継承されたハンドルは、元のハンドルと同じ値とアクセス特権を持っています。  
  
 *pCurrentDirectory*  
 現在のドライブと、新しいプロセス用のディレクトリを指定する null で終わる文字列へのポインター。 文字列は、ドライブ文字を含む完全パスである必要があります。 このパラメーターが NULL の場合、新しいプロセスは呼び出し元のプロセスとして、同じ現在のドライブとディレクトリがあります。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 **CreateProcessAsUser**を使用して、`CreateProcessAsUser`によって表されるユーザーのセキュリティ コンテキストで実行されている新しいプロセスを作成する Win32 関数、`CAccessToken`オブジェクトです。 説明を参照して、 [CreateProcessAsUser](http://msdn.microsoft.com/library/windows/desktop/ms682429)の必要なパラメーターの詳細については、関数です。  
  
 このメソッドが成功するため、`CAccessToken`オブジェクトは AssignPrimaryToken を保持する必要があります (ある場合を除いて、制限付きトークン) 実行します。  
  
##  <a name="createrestrictedtoken"></a>CAccessToken::CreateRestrictedToken  
 を新規作成するのには、このメソッドを呼び出す制限`CAccessToken`オブジェクトです。  
  
```
bool CreateRestrictedToken(
    CAccessToken* pRestrictedToken,
    const CTokenGroups& SidsToDisable,
    const CTokenGroups& SidsToRestrict,
    const CTokenPrivileges& PrivilegesToDelete = CTokenPrivileges()) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *pRestrictedToken*  
 新しい制限`CAccessToken`オブジェクトです。  
  
 `SidsToDisable`  
 A`CTokenGroups`拒否専用 Sid を指定するオブジェクト。  
  
 *SidsToRestrict*  
 A `CTokenGroups` Sid を制限を指定するオブジェクト。  
  
 `PrivilegesToDelete`  
 A`CTokenPrivileges`制限付きトークンで削除する権限を指定するオブジェクト。 既定では、空のオブジェクトを作成します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 `CreateRestrictedToken`使用して、 [CreateRestrictedToken](http://msdn.microsoft.com/library/windows/desktop/aa446583)新しいを作成する Win32 関数`CAccessToken`制限付きのオブジェクト。  
  
> [!NOTE]
>  このメソッドは、Windows 2000 で利用可能なまたはそれ以降のみです。  
  
> [!IMPORTANT]
>  使用する場合`CreateRestrictedToken`、以下を確認する: 既存のトークンが有効な (そして、ユーザーが入っていない) と`SidsToDisable`と`PrivilegesToDelete`が有効 (かつユーザーが入っていない)。 メソッドが false を返した場合は、機能を拒否します。  
  
##  <a name="detach"></a>CAccessToken::Detach  
 このメソッドを呼び出してアクセス トークンの所有権を放棄します。  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ハンドルを返す、`CAccessToken`がデタッチされます。  
  
### <a name="remarks"></a>コメント  
 このメソッドを取り消し、`CAccessToken`のアクセス トークンの所有者。  
  
##  <a name="disableprivilege"></a>CAccessToken::DisablePrivilege  
 権限を無効にするには、このメソッドを呼び出す、`CAccessToken`オブジェクトです。  
  
```
bool DisablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszPrivilege`  
 無効にするための権限を含む文字列へのポインター、`CAccessToken`オブジェクトです。  
  
 `pPreviousState`  
 ポインター、`CTokenPrivileges`特権の以前の状態を格納するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="disableprivileges"></a>CAccessToken::DisablePrivileges  
 1 つ以上の特権を無効にするには、このメソッドを呼び出す、`CAccessToken`オブジェクトです。  
  
```
bool DisablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rPrivileges`  
 無効にするための特権を含む文字列の配列へのポインター、`CAccessToken`オブジェクトです。  
  
 `pPreviousState`  
 ポインター、`CTokenPrivileges`特権の以前の状態を格納するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="enableprivilege"></a>CAccessToken::EnablePrivilege  
 特権を有効にするには、このメソッドを呼び出す、`CAccessToken`オブジェクトです。  
  
```
bool EnablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszPrivilege`  
 有効にするための権限を含む文字列へのポインター、`CAccessToken`オブジェクトです。  
  
 `pPreviousState`  
 ポインター、`CTokenPrivileges`特権の以前の状態を格納するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="enableprivileges"></a>CAccessToken::EnablePrivileges  
 1 つ以上の特権を有効にするには、このメソッドを呼び出す、`CAccessToken`オブジェクトです。  
  
```
bool EnablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rPrivileges`  
 有効にするための特権を含む文字列の配列へのポインター、`CAccessToken`オブジェクトです。  
  
 `pPreviousState`  
 ポインター、`CTokenPrivileges`特権の以前の状態を格納するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="getdefaultdacl"></a>CAccessToken::GetDefaultDacl  
 返すには、このメソッドを呼び出して、`CAccessToken`オブジェクトの DACL を既定値です。  
  
```
bool GetDefaultDacl(CDacl* pDacl) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDacl`  
 ポインター、 [CDacl クラス](../../atl/reference/cdacl-class.md)オブジェクトを受け取る、 **CAccessToken**オブジェクトの DACL を既定値です。  
  
### <a name="return-value"></a>戻り値  
 既定の DACL がされている場合、false を回復したそれ以外の場合は true を返します。  
  
##  <a name="geteffectivetoken"></a>CAccessToken::GetEffectiveToken  
 このメソッドを呼び出して取得、`CAccessToken`現在のスレッドに対して有効アクセス トークンと等しいオブジェクト。  
  
```
bool GetEffectiveToken(DWORD dwDesiredAccess) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDesiredAccess`  
 アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="getgroups"></a>CAccessToken::GetGroups  
 返すには、このメソッドを呼び出して、`CAccessToken`トークンのオブジェクトのグループです。  
  
```
bool GetGroups(CTokenGroups* pGroups) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *pGroups*  
 ポインター、 [CTokenGroups クラス](../../atl/reference/ctokengroups-class.md)グループ情報を受け取るオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="gethandle"></a>CAccessToken::GetHandle  
 アクセス トークンを識別するハンドルを取得するには、このメソッドを呼び出します。  
  
```
HANDLE GetHandle() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 ハンドルを返す、`CAccessToken`オブジェクトのアクセス トークンです。  
  
##  <a name="getimpersonationlevel"></a>CAccessToken::GetImpersonationLevel  
 アクセス トークンから偽装レベルを取得するには、このメソッドを呼び出します。  
  
```
bool GetImpersonationLevel(
    SECURITY_IMPERSONATION_LEVEL* pImpersonationLevel) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *pImpersonationLevel*  
 ポインター、 [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572)偽装レベルの情報が格納される列挙型。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="getlogonsessionid"></a>CAccessToken::GetLogonSessionId  
 関連付けられているログオン セッション ID を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。  
  
```
bool GetLogonSessionId(LUID* pluid) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pluid`  
 ポインター、 [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)ログオン セッション ID が表示されます  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 場合はデバッグ ビルドで、アサーション エラーが発生`pluid`は値が無効です。  
  
##  <a name="getlogonsid"></a>CAccessToken::GetLogonSid  
 関連付けられているログオン SID を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。  
  
```
bool GetLogonSid(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSid`  
 ポインター、 [CSid クラス](../../atl/reference/csid-class.md)オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 場合はデバッグ ビルドで、アサーション エラーが発生*pSid*は値が無効です。  
  
##  <a name="getowner"></a>CAccessToken::GetOwner  
 関連付けられている所有者を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。  
  
```
bool GetOwner(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSid`  
 ポインター、 [CSid クラス](../../atl/reference/csid-class.md)オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 所有者は、既定ではこのアクセス トークンが有効なときに作成されたオブジェクトに設定されます。  
  
##  <a name="getprimarygroup"></a>CAccessToken::GetPrimaryGroup  
 関連付けられているプライマリ グループを取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。  
  
```
bool GetPrimaryGroup(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSid`  
 ポインター、 [CSid クラス](../../atl/reference/csid-class.md)オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 グループは既定ではこのアクセス トークンが有効なときに作成されたオブジェクトに設定されます。  
  
##  <a name="getprivileges"></a>CAccessToken::GetPrivileges  
 関連付けられている権限を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。  
  
```
bool GetPrivileges(CTokenPrivileges* pPrivileges) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPrivileges`  
 ポインター、 [CTokenPrivileges クラス](../../atl/reference/ctokenprivileges-class.md)特権を受け取るオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="getprocesstoken"></a>CAccessToken::GetProcessToken  
 指定されたプロセスからアクセス トークンを使用して `CAccessToken` を初期化するには、このメソッドを呼び出します。  
  
```
bool GetProcessToken(DWORD dwDesiredAccess, HANDLE hProcess = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDesiredAccess`  
 アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。  
  
 *hProcess*  
 アクセス トークンが開いているプロセスへのハンドル。 `NULL` の既定値を使用すると、現在のプロセスが使用されます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は、`true` を返します。それ以外の場合は、`false` を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出し、 [OpenProcessToken](http://msdn.microsoft.com/library/aa379295\(vs.85\).aspx) Win32 関数です。  
  
##  <a name="getprofile"></a>CAccessToken::GetProfile  
 関連付けられたユーザー プロファイルを指すハンドルを取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。  
  
```
HANDLE GetProfile() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 プロファイルが存在しない場合、ユーザー プロファイル、または NULL を指すハンドルを返します。  
  
##  <a name="getsource"></a>CAccessToken::GetSource  
 ソースを取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。  
  
```
bool GetSource(TOKEN_SOURCE* pSource) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *pSource*  
 ポインター、 [TOKEN_SOURCE](http://msdn.microsoft.com/library/windows/desktop/aa379631)構造体。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="getstatistics"></a>CAccessToken::GetStatistics  
 関連付けられている情報を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。  
  
```
bool GetStatistics(TOKEN_STATISTICS* pStatistics) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *pStatistics*  
 ポインター、 [TOKEN_STATISTICS](http://msdn.microsoft.com/library/windows/desktop/aa379632)構造体。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="getterminalservicessessionid"></a>CAccessToken::GetTerminalServicesSessionId  
 関連付けられているターミナル サービス セッションの ID を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。  
  
```
bool GetTerminalServicesSessionId(DWORD* pdwSessionId) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *pdwSessionId*  
 ターミナル サービス セッションの id。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="getthreadtoken"></a>CAccessToken::GetThreadToken  
 初期化するには、このメソッドを呼び出して、`CAccessToken`特定のスレッドからのトークンに置き換えます。  
  
```
bool GetThreadToken(
    DWORD dwDesiredAccess,
    HANDLE hThread = NULL,
    bool bOpenAsSelf = true) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDesiredAccess`  
 アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。  
  
 `hThread`  
 アクセス トークンが開いているスレッドへのハンドルします。  
  
 `bOpenAsSelf`  
 アクセス チェックのスレッドの呼び出し元のセキュリティ コンテキストに対して行われるかどうかを示す、`GetThreadToken`メソッドで、または呼び出し元のスレッドのプロセスのセキュリティ コンテキスト。  
  
 このパラメーターが false の場合は、呼び出し元のスレッドのセキュリティ コンテキストを使用してアクセス チェックが実行されます。 スレッドは、クライアントを偽装する場合、クライアント プロセスのことをこのセキュリティ コンテキストにできます。 このパラメーターが true の場合、呼び出し元のスレッドのプロセスのセキュリティ コンテキストを使用してアクセス チェックを実行します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="gettokenid"></a>CAccessToken::GetTokenId  
 関連付けられているトークンの ID を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。  
  
```
bool GetTokenId(LUID* pluid) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pluid`  
 ポインター、 [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)トークンの ID を受け取ります  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="gettype"></a>CAccessToken::GetType  
 トークンの種類を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。  
  
```
bool GetType(TOKEN_TYPE* pType) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pType`  
 アドレス、 [TOKEN_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379633)成功した場合、トークンの種類を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 **TOKEN_TYPE**列挙型には、プライマリ トークンと偽装トークンを区別する値が含まれています。  
  
##  <a name="getuser"></a>CAccessToken::GetUser  
 関連付けられているユーザーを識別するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。  
  
```
bool GetUser(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSid`  
 ポインター、 [CSid クラス](../../atl/reference/csid-class.md)オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="hkeycurrentuser"></a>CAccessToken::HKeyCurrentUser  
 関連付けられたユーザー プロファイルを指すハンドルを取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。  
  
```
HKEY HKeyCurrentUser() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 プロファイルが存在しない場合、ユーザー プロファイル、または NULL を指すハンドルを返します。  
  
##  <a name="impersonate"></a>CAccessToken::Impersonate  
 権限の借用を割り当てるには、このメソッドを呼び出す`CAccessToken`スレッドにします。  
  
```
bool Impersonate(HANDLE hThread = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `hThread`  
 スレッドの偽装トークンを割り当てるへのハンドルします。 TOKEN_IMPERSONATE アクセス権を持つこのハンドルが開かれている必要があります。 場合`hThread`が NULL の場合、このメソッドによって、スレッドの偽装トークンの使用を停止します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 場合はデバッグ ビルドで、アサーション エラーが発生`CAccessToken`トークンへの有効なポインターがありません。  
  
 [CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)権限を借用したアクセス トークンを自動的に元に戻すために使用できます。  
  
##  <a name="impersonateloggedonuser"></a>CAccessToken::ImpersonateLoggedOnUser  
 呼び出し元スレッドでは、ログオン ユーザーのセキュリティ コンテキストを偽装を許可するようにこのメソッドを呼び出します。  
  
```
bool ImpersonateLoggedOnUser() const throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
  
> [!IMPORTANT]
>  偽装関数を呼び出すには、何らかの理由で失敗すると、クライアントを偽装できませんし、クライアントの要求が呼び出しを行ったプロセスのセキュリティ コンテキストで行われます。 プロセスが、高い特権を持つアカウントとして実行されているか、管理グループのメンバーは、ユーザーが操作を行うことがあるかどうかは許可されません。 そのため、この関数の戻り値常に確認する必要があります。  
  
##  <a name="istokenrestricted"></a>CAccessToken::IsTokenRestricted  
 場合にテストするには、このメソッドを呼び出して、`CAccessToken`オブジェクトには、制限付き Sid の一覧が含まれています。  
  
```
bool IsTokenRestricted() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 オブジェクトには、制限付き Sid、Sid を制限がない場合は false の一覧が含まれている場合、またはメソッドが失敗した場合は true を返します。  
  
##  <a name="loaduserprofile"></a>CAccessToken::LoadUserProfile  
 このメソッドに関連付けられているユーザー プロファイルの読み込みを呼び出して、`CAccessToken`オブジェクトです。  
  
```
bool LoadUserProfile() throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドで、アサーション エラーが発生場合、`CAccessToken`有効なトークンが含まれていないか、またはユーザーが既にプロファイルがします。  
  
##  <a name="logonuser"></a>CAccessToken::LogonUser  
 指定した資格情報に関連付けられているユーザーのログオン セッションを作成するには、このメソッドを呼び出します。  
  
```
bool LogonUser(
    LPCTSTR pszUserName,
    LPCTSTR pszDomain,
    LPCTSTR pszPassword,
    DWORD dwLogonType = LOGON32_LOGON_INTERACTIVE,
    DWORD dwLogonProvider = LOGON32_PROVIDER_DEFAULT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszUserName`  
 ユーザー名を指定する null で終わる文字列へのポインター。 これは、ログオンするユーザー アカウントの名前です。  
  
 *pszDomain*  
 ドメイン ユーザーまたはアカウントのデータベースを含むサーバーの名前を指定する null で終わる文字列へのポインター、`pszUserName`アカウントです。  
  
 `pszPassword`  
 指定されたユーザー アカウントのクリア テキスト パスワードを指定する null で終わる文字列へのポインター`pszUserName`します。  
  
 *dwLogonType*  
 実行するログオン操作の種類を指定します。 参照してください[LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184)詳細です。  
  
 *dwLogonProvider*  
 ログオンのプロバイダーを指定します。 参照してください[LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184)詳細です。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 関連付けられる、ログオンによるトークン、アクセス、`CAccessToken`です。 このメソッドが成功するため、`CAccessToken`オブジェクトの基本の信頼されたコンピューターの一部として保持者を識別する、SE_TCB_NAME 特権を保持する必要があります。 参照してください[LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184)必要な特権に関する詳細についてです。  
  
##  <a name="opencomclienttoken"></a>CAccessToken::OpenCOMClientToken  
 初期化するために、クライアントからの呼び出しを処理する COM サーバー内からこのメソッドを呼び出して、 `CAccessToken` COM クライアントからアクセス トークンを使用します。  
  
```
bool OpenCOMClientToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDesiredAccess`  
 アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。  
  
 `bImpersonate`  
 True の場合、この呼び出しが正常に完了した場合、現在のスレッドは呼び出し元の COM クライアントを偽装します。 False の場合、アクセス トークンが開きは、この呼び出しが完了したときに、スレッドに偽装トークンは与えられません。  
  
 `bOpenAsSelf`  
 アクセス チェックのスレッドの呼び出し元のセキュリティ コンテキストに対して行われるかどうかを示す、 [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182)メソッドで、または呼び出し元のスレッドのプロセスのセキュリティ コンテキスト。  
  
 このパラメーターが false の場合は、呼び出し元のスレッドのセキュリティ コンテキストを使用してアクセス チェックが実行されます。 スレッドは、クライアントを偽装する場合、クライアント プロセスのことをこのセキュリティ コンテキストにできます。 このパラメーターが true の場合、呼び出し元のスレッドのプロセスのセキュリティ コンテキストを使用してアクセス チェックを実行します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 [CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)を設定して作成された権限を借用したアクセス トークンを自動的に戻すには使用できる、`bImpersonate`フラグを*true*します。  
  
##  <a name="opennamedpipeclienttoken"></a>CAccessToken::OpenNamedPipeClientToken  
 初期化するために名前付きパイプ経由でこのメソッドは、サーバー内から作成要求を呼び出す、`CAccessToken`クライアントからアクセス トークンを使用します。  
  
```
bool OpenNamedPipeClientToken(
    HANDLE hPipe,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *hPipe*  
 名前付きパイプへのハンドルします。  
  
 `dwDesiredAccess`  
 アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。  
  
 `bImpersonate`  
 True の場合、この呼び出しが正常に完了した場合、現在のスレッドは呼び出し側のパイプ クライアントを偽装します。 False の場合、アクセス トークンが開きは、この呼び出しが完了したときに、スレッドに偽装トークンは与えられません。  
  
 `bOpenAsSelf`  
 アクセス チェックのスレッドの呼び出し元のセキュリティ コンテキストに対して行われるかどうかを示す、 [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182)メソッドで、または呼び出し元のスレッドのプロセスのセキュリティ コンテキスト。  
  
 このパラメーターが false の場合は、呼び出し元のスレッドのセキュリティ コンテキストを使用してアクセス チェックが実行されます。 スレッドは、クライアントを偽装する場合、クライアント プロセスのことをこのセキュリティ コンテキストにできます。 このパラメーターが true の場合、呼び出し元のスレッドのプロセスのセキュリティ コンテキストを使用してアクセス チェックを実行します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 [CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)を設定して作成された権限を借用したアクセス トークンを自動的に戻すには使用できる、`bImpersonate`フラグを*true*します。  
  
##  <a name="openrpcclienttoken"></a>CAccessToken::OpenRPCClientToken  
 初期化するには、RPC クライアントから呼び出しを処理するサーバー内からこのメソッドを呼び出して、`CAccessToken`クライアントからアクセス トークンを使用します。  
  
```
bool OpenRPCClientToken(
    RPC_BINDING_HANDLE BindingHandle,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *BindingHandle*  
 クライアントへのバインドを表す、サーバー上のハンドルをバインドします。  
  
 `dwDesiredAccess`  
 アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。  
  
 `bImpersonate`  
 True の場合、この呼び出しが正常に完了した場合、現在のスレッドは呼び出し元の RPC クライアントを偽装します。 False の場合、アクセス トークンが開きは、この呼び出しが完了したときに、スレッドに偽装トークンは与えられません。  
  
 `bOpenAsSelf`  
 アクセス チェックのスレッドの呼び出し元のセキュリティ コンテキストに対して行われるかどうかを示す、 [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182)メソッドで、または呼び出し元のスレッドのプロセスのセキュリティ コンテキスト。  
  
 このパラメーターが false の場合は、呼び出し元のスレッドのセキュリティ コンテキストを使用してアクセス チェックが実行されます。 スレッドは、クライアントを偽装する場合、クライアント プロセスのことをこのセキュリティ コンテキストにできます。 このパラメーターが true の場合、呼び出し元のスレッドのプロセスのセキュリティ コンテキストを使用してアクセス チェックを実行します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 [CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)を設定して作成された権限を借用したアクセス トークンを自動的に戻すには使用できる、`bImpersonate`フラグを*true*します。  
  
##  <a name="openthreadtoken"></a>CAccessToken::OpenThreadToken  
 偽装レベルを設定し、初期化するには、このメソッドを呼び出して、`CAccessToken`特定のスレッドからのトークンに置き換えます。  
  
```
bool OpenThreadToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDesiredAccess`  
 アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。  
  
 `bImpersonate`  
 True の場合、メソッドの完了後に、スレッド名は要求された偽装レベルのままします。 False の場合、スレッドは元の偽装レベルに戻ります。  
  
 `bOpenAsSelf`  
 アクセス チェックのスレッドの呼び出し元のセキュリティ コンテキストに対して行われるかどうかを示す、 [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182)メソッドで、または呼び出し元のスレッドのプロセスのセキュリティ コンテキスト。  
  
 このパラメーターが false の場合は、呼び出し元のスレッドのセキュリティ コンテキストを使用してアクセス チェックが実行されます。 スレッドは、クライアントを偽装する場合、クライアント プロセスのことをこのセキュリティ コンテキストにできます。 このパラメーターが true の場合、呼び出し元のスレッドのプロセスのセキュリティ コンテキストを使用してアクセス チェックを実行します。  
  
 `sil`  
 指定する[SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572)トークンの偽装レベルを提供する型を列挙します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 `OpenThreadToken`ような[CAccessToken::GetThreadToken](#getthreadtoken)が初期化する前に、偽装レベルを設定、`CAccessToken`スレッドのアクセス トークンからです。  
  
 [CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)を設定して作成された権限を借用したアクセス トークンを自動的に戻すには使用できる、`bImpersonate`フラグを*true*します。  
  
##  <a name="privilegecheck"></a>CAccessToken::PrivilegeCheck  
 指定された権限のセットが有効にするかどうかを判断するには、このメソッドを呼び出して、 **CAccessToken**オブジェクトです。  
  
```
bool PrivilegeCheck(
    PPRIVILEGE_SET RequiredPrivileges,
     bool* pbResult) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *RequiredPrivileges*  
 ポインター、 [PRIVILEGE_SET](http://msdn.microsoft.com/library/windows/desktop/aa379307)構造体。  
  
 *pbResult*  
 メソッドは設定で指定した権限の一部またはすべてが有効にするかどうかを示す値へのポインター、`CAccessToken`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 `PrivilegeCheck`が返される、**属性**のそれぞれに所属[LUID_AND_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379263)対応する特権が有効になっている場合は、構造体を SE_PRIVILEGE_USED_FOR_ACCESS に設定します。 このメソッドは、 [PrivilegeCheck](http://msdn.microsoft.com/library/windows/desktop/aa379304) Win32 関数です。  
  
##  <a name="revert"></a>CAccessToken::Revert  
 権限借用トークンを使用してスレッドを停止するには、このメソッドを呼び出します。  
  
```
bool Revert(HANDLE hThread = NULL) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hThread`  
 偽装を元に戻すスレッドへのハンドルします。 場合*hThread*が NULL の場合、現在のスレッドが前提としています。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 権限借用トークンのバージョンを再設定で自動的に実行できる、 [CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)します。  
  
##  <a name="setdefaultdacl"></a>CAccessToken::SetDefaultDacl  
 既定値を設定するには、このメソッドを呼び出すの DACL、`CAccessToken`オブジェクトです。  
  
```
bool SetDefaultDacl(const CDacl& rDacl) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rDacl`  
 新しい既定[CDacl クラス](../../atl/reference/cdacl-class.md)情報。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 既定の DACL は、新しいオブジェクトがこのアクセス トークンが有効で作成されるときに、既定で使用される DACL です。  
  
##  <a name="setowner"></a>CAccessToken::SetOwner  
 所有者を設定するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。  
  
```
bool SetOwner(const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rSid`  
 [CSid クラス](../../atl/reference/csid-class.md)所有者情報を含むオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 所有者は、このアクセス トークンが有効なときに作成された新しいオブジェクトに使用される既定の所有者です。  
  
##  <a name="setprimarygroup"></a>CAccessToken::SetPrimaryGroup  
 プライマリ グループを設定するには、このメソッドを呼び出して、`CAccessToken`オブジェクトです。  
  
```
bool SetPrimaryGroup(const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rSid`  
 [CSid クラス](../../atl/reference/csid-class.md)プライマリ グループの情報を格納するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 プライマリ グループは、このアクセス トークンが有効なときに作成された新しいオブジェクトの既定のグループです。  
  
## <a name="see-also"></a>関連項目  
 [ATLSecurity サンプル](../../visual-cpp-samples.md)   
 [アクセス トークン](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [クラスの概要](../../atl/atl-class-overview.md)

