---
title: "セキュリティに関するグローバル関数 |Microsoft ドキュメント"
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
- SIDs [C++], modifying SID objects
- ACL object global functions
- security IDs [C++]
ms.assetid: 6a584bfe-16b7-47f4-8439-9c789c41567a
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
ms.openlocfilehash: 368da76305910a0948eb386990a4bcdb84e61396
ms.lasthandoff: 02/24/2017

---
# <a name="security-global-functions"></a>セキュリティに関するグローバル関数
これらの関数は、SID および ACL オブジェクトを変更するためのサポートを提供します。  
  
> [!IMPORTANT]
>  実行するアプリケーションでは、次の表に示されている関数を使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
|||  
|-|-|  
|[AtlGetDacl](#atlgetdacl)|指定されたオブジェクトの随意アクセス制御リスト (DACL: Discretionary Access Control List) の情報を取得します。|  
|[AtlSetDacl](#atlsetdacl)|指定されたオブジェクトの随意アクセス制御リスト (DACL: Discretionary Access Control List) の情報を設定します。|  
|[AtlGetGroupSid](#atlgetgroupsid)|オブジェクトのグループ セキュリティ識別子 (SID: Security Identifier) を取得します。|  
|[AtlSetGroupSid](#atlsetgroupsid)|オブジェクトのグループ セキュリティ識別子 (SID: Security Identifier) を設定します。|  
|[AtlGetOwnerSid](#atlgetownersid)|オブジェクトの所有者セキュリティ識別子 (SID: Security Identifier) を取得します。|  
|[AtlSetOwnerSid](#atlsetownersid)|オブジェクトの所有者セキュリティ識別子 (SID: Security Identifier) を設定します。|  
|[AtlGetSacl](#atlgetsacl)|指定されたオブジェクトのシステム アクセス制御リスト (SACL: System Access Control List) の情報を取得します。|  
|[AtlSetSacl](#atlsetsacl)|指定されたオブジェクトのシステム アクセス制御リスト (SACL: System Access Control List) の情報を設定します。|  
|[AtlGetSecurityDescriptor](#atlgetsecuritydescriptor)|指定されたオブジェクトのセキュリティ記述子を取得します。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h 

##  <a name="a-nameatlgetdacla--atlgetdacl"></a><a name="atlgetdacl"></a>AtlGetDacl  
 指定されたオブジェクトの随意アクセス制御リスト (DACL: Discretionary Access Control List) の情報を取得します。  
  
> [!IMPORTANT]
>  実行するアプリケーションでこの関数は使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
```
inline bool AtlGetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CDacl* pDacl) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 セキュリティ情報を取得する対象となるオブジェクトへのハンドルします。  
  
 `ObjectType`  
 値を示す、 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593)をで識別されるオブジェクトの種類を示す列挙体、`hObject`パラメーター。  
  
 `pDacl`  
 取得したセキュリティ情報を含む DACL オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 いずれかデバッグ ビルドで、アサーション エラーが発生`hObject`または`pDacl`が正しくない*します。*  

v

##  <a name="a-nameatlsetdacla--atlsetdacl"></a><a name="atlsetdacl"></a>AtlSetDacl  
 指定されたオブジェクトの随意アクセス制御リスト (DACL: Discretionary Access Control List) の情報を設定します。  
  
> [!IMPORTANT]
>  実行するアプリケーションでこの関数は使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
```
inline bool AtlSetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CDacl& rDacl,
    DWORD dwInheritanceFlowControl = 0) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 セキュリティ情報を設定する対象となるオブジェクトへのハンドルします。  
  
 `ObjectType`  
 値を示す、 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593)をで識別されるオブジェクトの種類を示す列挙体、`hObject`パラメーター。  
  
 `rDacl`  
 新しいセキュリティ情報を含む DACL です。  
  
 `dwInheritanceFlowControl`  
 継承のフロー制御します。 この値は、0 (既定)、PROTECTED_DACL_SECURITY_INFORMATION または UNPROTECTED_DACL_SECURITY_INFORMATION を指定できます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 場合はデバッグ ビルドで、アサーション エラーが発生`hObject`が有効でない場合、または`dwInheritanceFlowControl`許可されている&3; つの値のいずれかではありません。  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h 

##  <a name="a-nameatlgetgroupsida--atlgetgroupsid"></a><a name="atlgetgroupsid"></a>AtlGetGroupSid  
 オブジェクトのグループ セキュリティ識別子 (SID: Security Identifier) を取得します。  
  
> [!IMPORTANT]
>  実行するアプリケーションでこの関数は使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
```
inline bool AtlGetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 セキュリティ情報を取得する対象のオブジェクトへのハンドルします。  
  
 `ObjectType`  
 値を示す、 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593)をで識別されるオブジェクトの種類を示す列挙体、`hObject`パラメーター。  
  
 `pSid`  
 ポインター、`CSid`オブジェクトは、新しいセキュリティ情報が含まれます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h 

##  <a name="a-nameatlsetgroupsida--atlsetgroupsid"></a><a name="atlsetgroupsid"></a>AtlSetGroupSid  
 オブジェクトのグループ セキュリティ識別子 (SID: Security Identifier) を設定します。  
  
> [!IMPORTANT]
>  実行するアプリケーションでこの関数は使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
```
inline bool AtlSetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 セキュリティ情報を設定する対象となるオブジェクトへのハンドルします。  
  
 `ObjectType`  
 値を示す、 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593)をで識別されるオブジェクトの種類を示す列挙体、`hObject`パラメーター。  
  
 `rSid`  
 `CSid`新しいセキュリティ情報を含むオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h 

##  <a name="a-nameatlgetownersida--atlgetownersid"></a><a name="atlgetownersid"></a>AtlGetOwnerSid  
 オブジェクトの所有者セキュリティ識別子 (SID: Security Identifier) を取得します。  
  
> [!IMPORTANT]
>  実行するアプリケーションでこの関数は使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
```
inline bool AtlGetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 セキュリティ情報を取得する対象のオブジェクトへのハンドルします。  
  
 `ObjectType`  
 値を示す、 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593)をで識別されるオブジェクトの種類を示す列挙体、`hObject`パラメーター。  
  
 `pSid`  
 ポインター、`CSid`オブジェクトは、新しいセキュリティ情報が含まれます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h 

##  <a name="a-nameatlsetownersida--atlsetownersid"></a><a name="atlsetownersid"></a>AtlSetOwnerSid  
 オブジェクトの所有者セキュリティ識別子 (SID: Security Identifier) を設定します。  
  
> [!IMPORTANT]
>  実行するアプリケーションでこの関数は使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
```
inline bool AtlSetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 セキュリティ情報を設定する対象となるオブジェクトへのハンドルします。  
  
 `ObjectType`  
 値を示す、 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593)をで識別されるオブジェクトの種類を示す列挙体、`hObject`パラメーター。  
  
 `rSid`  
 `CSid`新しいセキュリティ情報を含むオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h 

##  <a name="a-nameatlgetsacla--atlgetsacl"></a><a name="atlgetsacl"></a>AtlGetSacl  
 指定されたオブジェクトのシステム アクセス制御リスト (SACL: System Access Control List) の情報を取得します。  
  
> [!IMPORTANT]
>  実行するアプリケーションでこの関数は使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
```
inline bool AtlGetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSacl* pSacl,
    bool bRequestNeededPrivileges = true) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 セキュリティ情報を取得する対象のオブジェクトへのハンドルします。  
  
 `ObjectType`  
 値を示す、 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593)をで識別されるオブジェクトの種類を示す列挙体、`hObject`パラメーター。  
  
 `pSacl`  
 取得したセキュリティ情報を含む SACL オブジェクトへのポインター。  
  
 `bRequestNeededPrivileges`  
 True の場合は、関数を SE_SECURITY_NAME 特権を有効にして、完了時に復元を試みます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 場合`AtlGetSacl`が何度もを多数の異なるオブジェクトで呼び出されると、関数を呼び出す前に&1; 回 SE_SECURITY_NAME 特権を有効にする方が効率的になります`bRequestNeededPrivileges`を false に設定します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h 

##  <a name="a-nameatlsetsacla--atlsetsacl"></a><a name="atlsetsacl"></a>AtlSetSacl  
 指定されたオブジェクトのシステム アクセス制御リスト (SACL: System Access Control List) の情報を設定します。  
  
> [!IMPORTANT]
>  実行するアプリケーションでこの関数は使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
```
inline bool AtlSetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSacl& rSacl,
    DWORD dwInheritanceFlowControl = 0,
    bool bRequestNeededPrivileges = true) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 セキュリティ情報を設定する対象となるオブジェクトへのハンドルします。  
  
 `ObjectType`  
 値を示す、 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593)をで識別されるオブジェクトの種類を示す列挙体、`hObject`パラメーター。  
  
 *rSacl*  
 新しいセキュリティ情報を含む SACL です。  
  
 `dwInheritanceFlowControl`  
 継承のフロー制御します。 この値は、0 (既定)、PROTECTED_SACL_SECURITY_INFORMATION または UNPROTECTED_SACL_SECURITY_INFORMATION を指定できます。  
  
 `bRequestNeededPrivileges`  
 True の場合は、関数を SE_SECURITY_NAME 特権を有効にして、完了時に復元を試みます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 場合はデバッグ ビルドで、アサーション エラーが発生`hObject`が有効でない場合、または`dwInheritanceFlowControl`許可されている&3; つの値のいずれかではありません。  
  
 場合`AtlSetSacl`が何度もを多数の異なるオブジェクトで呼び出されると、関数を呼び出す前に&1; 回 SE_SECURITY_NAME 特権を有効にする方が効率的になります`bRequestNeededPrivileges`を false に設定します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h 

##  <a name="a-nameatlgetsecuritydescriptora--atlgetsecuritydescriptor"></a><a name="atlgetsecuritydescriptor"></a>AtlGetSecurityDescriptor  
 指定されたオブジェクトのセキュリティ記述子を取得します。  
  
> [!IMPORTANT]
>  実行するアプリケーションでこの関数は使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
```
inline bool AtlGetSecurityDescriptor(
    LPCTSTR pszObjectName,
    SE_OBJECT_TYPE ObjectType,
    CSecurityDesc* pSecurityDescriptor,
    SECURITY_INFORMATION requestedInfo = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION,
 bool bRequestNeededPrivileges = true) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *pszObjectName*  
 セキュリティ情報を取得する対象のオブジェクトの名前を指定する null で終わる文字列へのポインター。  
  
 `ObjectType`  
 値を示す、 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593)をで識別されるオブジェクトの種類を示す列挙体、 *pszObjectName*パラメーター。  
  
 *pSecurityDescriptor*  
 要求されたセキュリティ記述子を受け取るオブジェクトです。  
  
 *requestedInfo*  
 一連の[SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573)ビットを取得するセキュリティ情報の種類を示すフラグ。 このパラメーターは、次の値の組み合わせを指定できます。  
  
 `bRequestNeededPrivileges`  
 True の場合は、関数を SE_SECURITY_NAME 特権を有効にして、完了時に復元を試みます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 場合`AtlGetSecurityDescriptor`が何度もを多数の異なるオブジェクトで呼び出されると、関数を呼び出す前に&1; 回 SE_SECURITY_NAME 特権を有効にする方が効率的になります`bRequestNeededPrivileges`を false に設定します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h 
   
## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)

