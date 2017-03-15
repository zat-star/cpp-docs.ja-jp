---
title: "セキュリティ識別子のグローバル関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- security IDs [C++]
- SIDs [C++], returning SID objects
ms.assetid: 85404dcb-c59b-4535-ab3d-66cfa37e87de
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 9e51fe30b0519514df34f1a77b1e731f51047520
ms.lasthandoff: 02/24/2017

---
# <a name="security-identifier-global-functions"></a>セキュリティ識別子のグローバル関数
これらの関数は、オブジェクトに共通のよく知られた SID を返します。  
  
> [!IMPORTANT]
>  実行するアプリケーションでは、次の表に示されている関数を使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
|||  
|-|-|  
|[Sids::AccountOps](#accountops)|DOMAIN_ALIAS_RID_ACCOUNT_OPS SID を返します。|  
|[Sids::Admins](#admins)|DOMAIN_ALIAS_RID_ADMINS SID を返します。|  
|[Sids::AnonymousLogon](#anonymouslogon)|SECURITY_ANONYMOUS_LOGON_RID SID を返します。|  
|[Sids::AuthenticatedUser](#authenticateduser)|SECURITY_AUTHENTICATED_USER_RID SID を返します。|  
|[Sids::BackupOps](#backupops)|DOMAIN_ALIAS_RID_BACKUP_OPS SID を返します。|  
|[Sids::Batch](#batch)|SECURITY_BATCH_RID SID を返します。|  
|[Sids::CreatorGroup](#creatorgroup)|SECURITY_CREATOR_GROUP_RID SID を返します。|  
|[Sids::CreatorGroupServer](#creatorgroupserver)|SECURITY_CREATOR_GROUP_SERVER_RID SID を返します。|  
|[Sids::CreatorOwner](#creatorowner)|SECURITY_CREATOR_OWNER_RID SID を返します。|  
|[Sids::CreatorOwnerServer](#creatorownerserver)|SECURITY_CREATOR_OWNER_SERVER_RID SID を返します。|  
|[Sids::Dialup](#dialup)|SECURITY_DIALUP_RID SID を返します。|  
|[Sids::Guests](#guests)|DOMAIN_ALIAS_RID_GUESTS SID を返します。|  
|[Sids::Interactive](#interactive)|SECURITY_INTERACTIVE_RID SID を返します。|  
|[Sids::Local](#local)|SECURITY_LOCAL_RID SID を返します。|  
|[Sids::Network](#network)|SECURITY_NETWORK_RID SID を返します。|  
|[Sids::NetworkService](#networkservice)|SECURITY_NETWORK_SERVICE_RID SID を返します。|  
|[Sids::Null](#null)|SECURITY_NULL_RID SID を返します。|  
|[Sids::PreW2KAccess](#prew2kaccess)|DOMAIN_ALIAS_RID_PREW2KCOMPACCESS SID を返します。|  
|[Sids::PowerUsers](#powerusers)|DOMAIN_ALIAS_RID_POWER_USERS SID を返します。|  
|[Sids::PrintOps](#printops)|DOMAIN_ALIAS_RID_PRINT_OPS SID を返します。|  
|[Sids::Proxy](#proxy)|SECURITY_PROXY_RID SID を返します。|  
|[Sids::RasServers](#rasservers)|DOMAIN_ALIAS_RID_RAS_SERVERS SID を返します。|  
|[Sids::Replicator](#replicator)|DOMAIN_ALIAS_RID_REPLICATOR SID を返します。|  
|[Sids::RestrictedCode](#restrictedcode)|SECURITY_RESTRICTED_CODE_RID SID を返します。|  
|[Sids::Self](#self)|SECURITY_PRINCIPAL_SELF_RID SID を返します。|  
|[Sids::ServerLogon](#serverlogon)|SECURITY_SERVER_LOGON_RID SID を返します。|  
|[Sids::Service](#service)|SECURITY_SERVICE_RID SID を返します。|  
|[Sids::System](#system)|SECURITY_LOCAL_SYSTEM_RID SID を返します。|  
|[Sids::SystemOps](#systemops)|DOMAIN_ALIAS_RID_SYSTEM_OPS SID を返します。|  
|[Sids::TerminalServer](#terminalserver)|SECURITY_TERMINAL_SERVER_RID SID を返します。|  
|[Sids::Users](#users)|DOMAIN_ALIAS_RID_USERS SID を返します。|  
|[Sids::World](#world)|SECURITY_WORLD_RID SID を返します。|  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h 

##  <a name="a-nameaccountopsa--sidsaccountops"></a><a name="accountops"></a>Sids::AccountOps  
 DOMAIN_ALIAS_RID_ACCOUNT_OPS SID を返します。    
  
```
CSid AccountOps() throw(...);
```  
  
##  <a name="a-nameadminsa--sidsadmins"></a><a name="admins"></a>Sids::Admins  
 DOMAIN_ALIAS_RID_ADMINS SID を返します。  
```
CSid Admins() throw(...);
```  
  
##  <a name="a-nameanonymouslogona--sidsanonymouslogon"></a><a name="anonymouslogon"></a>Sids::AnonymousLogon  
 SECURITY_ANONYMOUS_LOGON_RID SID を返します。  
```
CSid AnonymousLogon() throw(...);
```  
  
##  <a name="a-nameauthenticatedusera--sidsauthenticateduser"></a><a name="authenticateduser"></a>Sids::AuthenticatedUser  
 SECURITY_AUTHENTICATED_USER_RID SID を返します。  
```
CSid AuthenticatedUser() throw(...);
```  
  
##  <a name="a-namebackupopsa--sidsbackupops"></a><a name="backupops"></a>Sids::BackupOps  
 DOMAIN_ALIAS_RID_BACKUP_OPS SID を返します。  
```
CSid BackupOps() throw(...);
```  
  
##  <a name="a-namebatcha--sidsbatch"></a><a name="batch"></a>Sids::Batch  
 SECURITY_BATCH_RID SID を返します。  
```
CSid Batch() throw(...);
```  
  
##  <a name="a-namecreatorgroupa--sidscreatorgroup"></a><a name="creatorgroup"></a>Sids::CreatorGroup  
 SECURITY_CREATOR_GROUP_RID SID を返します。  
```
CSid CreatorGroup() throw(...);
```  
  
##  <a name="a-namecreatorgroupservera--sidscreatorgroupserver"></a><a name="creatorgroupserver"></a>Sids::CreatorGroupServer  
 SECURITY_CREATOR_GROUP_SERVER_RID SID を返します。  
```
CSid CreatorGroupServer() throw(...);
```  
  
##  <a name="a-namecreatorownera--sidscreatorowner"></a><a name="creatorowner"></a>Sids::CreatorOwner  
 SECURITY_CREATOR_OWNER_RID SID を返します。  
```
CSid CreatorOwner() throw(...);
```  
  
##  <a name="a-namecreatorownerservera--sidscreatorownerserver"></a><a name="creatorownerserver"></a>Sids::CreatorOwnerServer  
 SECURITY_CREATOR_OWNER_SERVER_RID SID を返します。  
```
CSid CreatorOwnerServer() throw(...);
```  
  
##  <a name="a-namedialupa--sidsdialup"></a><a name="dialup"></a>Sids::Dialup  
 SECURITY_DIALUP_RID SID を返します。  
```
CSid Dialup() throw(...);
```  
  
##  <a name="a-nameguestsa--sidsguests"></a><a name="guests"></a>Sids::Guests  
 DOMAIN_ALIAS_RID_GUESTS SID を返します。  
```
CSid Guests() throw(...);
```  
  
##  <a name="a-nameinteractivea--sidsinteractive"></a><a name="interactive"></a>Sids::Interactive  
 SECURITY_INTERACTIVE_RID SID を返します。  
```
CSid Interactive() throw(...);
```  
  
##  <a name="a-namelocala--sidslocal"></a><a name="local"></a>Sids::Local  
 SECURITY_LOCAL_RID SID を返します。  
```
CSid Local() throw(...);
```  
  
##  <a name="a-namenetworka--sidsnetwork"></a><a name="network"></a>Sids::Network  
 SECURITY_NETWORK_RID SID を返します。  
```
CSid Network() throw(...);
```  
  
##  <a name="a-namenetworkservicea--sidsnetworkservice"></a><a name="networkservice"></a>Sids::NetworkService  
 SECURITY_NETWORK_SERVICE_RID SID を返します。  
```
CSid NetworkService() throw(...);
```  
  
### <a name="remarks"></a>コメント  
 CPerfMon セキュリティ オブジェクトの読み取りに NT authority \networkservice ユーザーを有効にするのにには、NetworkService を使用します。 NetworkService、SecurityAttribute を DLL に NetworkService アカウントでログインすることができる ATLServer コードに追加する[!INCLUDE[WinXpFamily](../../atl/reference/includes/winxpfamily_md.md)]とオペレーティング システムを大きくします。  
  
 カスタム ログのカウンターがパフォーマンス モニター MMC で ATLServer CPerfMon クラスを使用して作成されると、リアルタイムのビューに正しく表示されますが、ログ ファイルを表示するときに、カウンターが表示されません。 CPerfMon カスタム パフォーマンス カウンターでは、「パフォーマンス ログと警告」サービス (smlogsvc.exe) の下で実行するために必要な権限がない[!INCLUDE[WinXpFamily](../../atl/reference/includes/winxpfamily_md.md)](またはそれ以上) のオペレーティング システムです。 このサービスは、"NT authority \networkservice"アカウントで実行されます。  
  
##  <a name="a-namenulla--sidsnull"></a><a name="null"></a>Sids::Null  
 SECURITY_NULL_RID SID を返します。  
```
CSid Null() throw(...);
```  
  
##  <a name="a-nameprew2kaccessa--sidsprew2kaccess"></a><a name="prew2kaccess"></a>Sids::PreW2KAccess  
 DOMAIN_ALIAS_RID_PREW2KCOMPACCESS SID を返します。  
```
CSid PreW2KAccess() throw(...);
```  
  
##  <a name="a-namepowerusersa--sidspowerusers"></a><a name="powerusers"></a>Sids::PowerUsers  
 DOMAIN_ALIAS_RID_POWER_USERS SID を返します。  
```
CSid PowerUsers() throw(...);
```  
  
##  <a name="a-nameprintopsa--sidsprintops"></a><a name="printops"></a>Sids::PrintOps  
 DOMAIN_ALIAS_RID_PRINT_OPS SID を返します。  
```
CSid PrintOps() throw(...);
```  
  
##  <a name="a-nameproxya--sidsproxy"></a><a name="proxy"></a>Sids::Proxy  
 SECURITY_PROXY_RID SID を返します。  
```
CSid Proxy() throw(...);
```  
  
##  <a name="a-namerasserversa--sidsrasservers"></a><a name="rasservers"></a>Sids::RasServers  
 DOMAIN_ALIAS_RID_RAS_SERVERS SID を返します。  
```
CSid RasServers() throw(...);
```  
  
##  <a name="a-namereplicatora--sidsreplicator"></a><a name="replicator"></a>Sids::Replicator  
 DOMAIN_ALIAS_RID_REPLICATOR SID を返します。  
```
CSid Replicator() throw(...);
```  
  
##  <a name="a-namerestrictedcodea--sidsrestrictedcode"></a><a name="restrictedcode"></a>Sids::RestrictedCode  
 SECURITY_RESTRICTED_CODE_RID SID を返します。  
```
CSid RestrictedCode() throw(...);
```  
  
##  <a name="a-nameselfa--sidsself"></a><a name="self"></a>Sids::Self  
 SECURITY_PRINCIPAL_SELF_RID SID を返します。  
```
CSid Self() throw(...);
```  
  
##  <a name="a-nameserverlogona--sidsserverlogon"></a><a name="serverlogon"></a>Sids::ServerLogon  
 SECURITY_SERVER_LOGON_RID SID を返します。  
```
CSid ServerLogon() throw(...);
```  
  
##  <a name="a-nameservicea--sidsservice"></a><a name="service"></a>Sids::Service  
 SECURITY_SERVICE_RID SID を返します。  
```
CSid Service() throw(...);
```  
  
##  <a name="a-namesystema--sidssystem"></a><a name="system"></a>Sids::System  
 SECURITY_LOCAL_SYSTEM_RID SID を返します。  
```
CSid System() throw(...);
```  
  
##  <a name="a-namesystemopsa--sidssystemops"></a><a name="systemops"></a>Sids::SystemOps  
 DOMAIN_ALIAS_RID_SYSTEM_OPS SID を返します。  
```
CSid SystemOps() throw(...);
```  
  
##  <a name="a-nameterminalservera--sidsterminalserver"></a><a name="terminalserver"></a>Sids::TerminalServer  
 SECURITY_TERMINAL_SERVER_RID SID を返します。  
```
CSid TerminalServer() throw(...);
```  
  
##  <a name="a-nameusersa--sidsusers"></a><a name="users"></a>Sids::Users  
 DOMAIN_ALIAS_RID_USERS SID を返します。  
```
CSid Users() throw(...);
```  
  
##  <a name="a-nameworlda--sidsworld"></a><a name="world"></a>Sids::World  
 SECURITY_WORLD_RID SID を返します。  
```
CSid World() throw(...);
```  
  
## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)

