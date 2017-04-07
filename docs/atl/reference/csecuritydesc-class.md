---
title: "CSecurityDesc クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc::CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc::FromString
- ATLSECURITY/ATL::CSecurityDesc::GetControl
- ATLSECURITY/ATL::CSecurityDesc::GetDacl
- ATLSECURITY/ATL::CSecurityDesc::GetGroup
- ATLSECURITY/ATL::CSecurityDesc::GetOwner
- ATLSECURITY/ATL::CSecurityDesc::GetPSECURITY_DESCRIPTOR
- ATLSECURITY/ATL::CSecurityDesc::GetSacl
- ATLSECURITY/ATL::CSecurityDesc::IsDaclAutoInherited
- ATLSECURITY/ATL::CSecurityDesc::IsDaclDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsDaclPresent
- ATLSECURITY/ATL::CSecurityDesc::IsDaclProtected
- ATLSECURITY/ATL::CSecurityDesc::IsGroupDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsOwnerDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsSaclAutoInherited
- ATLSECURITY/ATL::CSecurityDesc::IsSaclDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsSaclPresent
- ATLSECURITY/ATL::CSecurityDesc::IsSaclProtected
- ATLSECURITY/ATL::CSecurityDesc::IsSelfRelative
- ATLSECURITY/ATL::CSecurityDesc::MakeAbsolute
- ATLSECURITY/ATL::CSecurityDesc::MakeSelfRelative
- ATLSECURITY/ATL::CSecurityDesc::SetControl
- ATLSECURITY/ATL::CSecurityDesc::SetDacl
- ATLSECURITY/ATL::CSecurityDesc::SetGroup
- ATLSECURITY/ATL::CSecurityDesc::SetOwner
- ATLSECURITY/ATL::CSecurityDesc::SetSacl
- ATLSECURITY/ATL::CSecurityDesc::ToString
dev_langs:
- C++
helpviewer_keywords:
- CSecurityDesc class
ms.assetid: 3767a327-378f-4690-ba40-4d9f6a1f5ee4
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6dbd586ee3ee07d3c567fa0aae46446397dfb62b
ms.lasthandoff: 02/24/2017

---
# <a name="csecuritydesc-class"></a>CSecurityDesc クラス
このクラスは、用のラッパー、 **SECURITY_DESCRIPTOR**構造体。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CSecurityDesc
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSecurityDesc::CSecurityDesc](#csecuritydesc)|コンストラクターです。|  
|[CSecurityDesc:: ~ CSecurityDesc](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSecurityDesc::FromString](#fromstring)|有効な機能のセキュリティ記述子には、文字列形式のセキュリティ記述子を変換します。|  
|[CSecurityDesc::GetControl](#getcontrol)|取得は、セキュリティ記述子から情報を制御します。|  
|[CSecurityDesc::GetDacl](#getdacl)|セキュリティ記述子から随意アクセス制御リスト (DACL) の情報を取得します。|  
|[CSecurityDesc::GetGroup](#getgroup)|セキュリティ記述子からプライマリ グループの情報を取得します。|  
|[CSecurityDesc::GetOwner](#getowner)|セキュリティ記述子から所有者の情報を取得します。|  
|[CSecurityDesc::GetPSECURITY_DESCRIPTOR](#getpsecurity_descriptor)|ポインターを返す、 **SECURITY_DESCRIPTOR**構造体。|  
|[CSecurityDesc::GetSacl](#getsacl)|セキュリティ記述子からシステム アクセス制御リスト (SACL) 情報を取得します。|  
|[CSecurityDesc::IsDaclAutoInherited](#isdaclautoinherited)|自動適用をサポートするために、DACL が構成されているかどうかを判断します。|  
|[CSecurityDesc::IsDaclDefaulted](#isdacldefaulted)|セキュリティ記述子が既定の DACL に設定されているかどうかを判断します。|  
|[CSecurityDesc::IsDaclPresent](#isdaclpresent)|セキュリティ記述子に DACL が含まれているかどうかを判断します。|  
|[CSecurityDesc::IsDaclProtected](#isdaclprotected)|変更を防ぐ DACL が構成されているかどうかを判断します。|  
|[CSecurityDesc::IsGroupDefaulted](#isgroupdefaulted)|既定で設定されたセキュリティ記述子のグループ セキュリティ識別子 (SID) を決定します。|  
|[CSecurityDesc::IsOwnerDefaulted](#isownerdefaulted)|既定で設定されたセキュリティ記述子の所有者の SID を決定します。|  
|[CSecurityDesc::IsSaclAutoInherited](#issaclautoinherited)|自動適用をサポートするために、SACL が構成されているかどうかを判断します。|  
|[CSecurityDesc::IsSaclDefaulted](#issacldefaulted)|セキュリティ記述子が既定の SACL に設定されているかどうかを判断します。|  
|[CSecurityDesc::IsSaclPresent](#issaclpresent)|セキュリティ記述子に SACL が含まれているかどうかを判断します。|  
|[CSecurityDesc::IsSaclProtected](#issaclprotected)|変更を防ぐ、SACL が構成されているかどうかを判断します。|  
|[CSecurityDesc::IsSelfRelative](#isselfrelative)|セキュリティ記述子が自己相対形式のかどうかを判断します。|  
|[CSecurityDesc::MakeAbsolute](#makeabsolute)|セキュリティ記述子を絶対形式に変換するには、このメソッドを呼び出します。|  
|[CSecurityDesc::MakeSelfRelative](#makeselfrelative)|セキュリティ記述子を自己相対形式に変換するには、このメソッドを呼び出します。|  
|[CSecurityDesc::SetControl](#setcontrol)|セキュリティ記述子の制御ビットを設定します。|  
|[CSecurityDesc::SetDacl](#setdacl)|DACL で情報を設定します。 既に DACL が表示されている、セキュリティ記述子で置き換えられます。|  
|[CSecurityDesc::SetGroup](#setgroup)|既にあるすべてのプライマリ グループ情報を交換絶対形式のセキュリティ記述子のプライマリ グループの情報を設定します。|  
|[CSecurityDesc::SetOwner](#setowner)|所有者の情報が既に組み込まれている置換絶対形式のセキュリティ記述子の所有者の情報を設定します。|  
|[CSecurityDesc::SetSacl](#setsacl)|SACL の情報を設定します。 既に SACL が表示されている、セキュリティ記述子で置き換えられます。|  
|[CSecurityDesc::ToString](#tostring)|セキュリティ記述子を文字列形式に変換します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CSecurityDesc::operator const SECURITY_DESCRIPTOR *](#operator_const_security_descriptor__star)|ポインターを返す、 **SECURITY_DESCRIPTOR**構造体。|  
|[CSecurityDesc::operator =](#operator_eq)|代入演算子。|  
  
## <a name="remarks"></a>コメント  
 **SECURITY_DESCRIPTOR**構造体には、オブジェクトに関連付けられているセキュリティ情報が含まれています。 アプリケーションでは、この構造体を使用して設定し、オブジェクトのセキュリティ状態をクエリします。 関連項目[AtlGetSecurityDescriptor](http://msdn.microsoft.com/library/233578b8-dcc5-4f51-8e62-7cdcc2ff6b11)します。  
  
 アプリケーションは変更しないで、 **SECURITY_DESCRIPTOR**構造直接必要がありますクラス メソッド使用します。  
  
 Windows のアクセス制御モデルの概要については、次を参照してください。[アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h  
  
##  <a name="csecuritydesc"></a>CSecurityDesc::CSecurityDesc  
 コンストラクターです。  
  
```
CSecurityDesc() throw();
CSecurityDesc(const CSecurityDesc& rhs) throw(... );  
CSecurityDesc(const SECURITY_DESCRIPTOR& rhs) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 `CSecurityDesc`オブジェクトまたは**SECURITY_DESCRIPTOR**に割り当てる新しい構造`CSecurityDesc`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 `CSecurityDesc`を使用してオブジェクトを作成することができます必要に応じて、 **SECURITY_DESCRIPTOR**構造体または以前に定義された`CSecurityDesc`オブジェクトです。  
  
##  <a name="dtor"></a>CSecurityDesc:: ~ CSecurityDesc  
 デストラクターです。  
  
```
virtual ~CSecurityDesc() throw();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターは、割り当てられているすべてのリソースを解放します。  
  
##  <a name="fromstring"></a>CSecurityDesc::FromString  
 有効な機能のセキュリティ記述子には、文字列形式のセキュリティ記述子を変換します。  
  
```
bool FromString(LPCTSTR pstr) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstr`  
 含む null で終わる文字列へのポインター、[文字列形式のセキュリティ記述子](http://msdn.microsoft.com/library/windows/desktop/aa379570)変換します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合に true を返します。 失敗した場合は例外をスローします。  
  
### <a name="remarks"></a>コメント  
 使用して、文字列を作成することができます[CSecurityDesc::ToString](#tostring)します。 セキュリティ記述子を文字列に変換すると、格納および送信するやすくなります。  
  
 このメソッドは使用可能な Windows 2000 以降のバージョンとを呼び出すので[convertstringsecuritydescriptortosecuritydescriptor が](http://msdn.microsoft.com/library/windows/desktop/aa376401)です。  
  
##  <a name="getcontrol"></a>CSecurityDesc::GetControl  
 取得は、セキュリティ記述子から情報を制御します。  
  
```
bool GetControl(SECURITY_DESCRIPTOR_CONTROL* psdc) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *psdc*  
 ポインター、 **SECURITY_DESCRIPTOR_CONTROL**セキュリティ記述子の制御情報を受け取る。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、false、失敗した場合に true を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは Windows 2000 を使用するときに意味のある以降のみ、なさ[GetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa446647)します。  
  
##  <a name="getdacl"></a>CSecurityDesc::GetDacl  
 セキュリティ記述子から随意アクセス制御リスト (DACL) の情報を取得します。  
  
```
bool GetDacl(
    CDacl* pDacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDacl`  
 ポインター、`CDacl`セキュリティ記述子の DACL のコピーを格納する構造体。 随意**ACL**メソッドのセットが存在する`pDacl`セキュリティのアドレス記述子の随意**ACL**します。 随意**ACL**が存在しない値は格納されません。  
  
 `pbPresent`  
 随意の存在を示す値を指すポインター **ACL**で指定されたセキュリティ記述子。 セキュリティ記述子が随意が含まれる場合**ACL**、このパラメーターの設定を true にします。 セキュリティ記述子は、随意に含まれない場合**ACL**、このパラメーターが false に設定します。  
  
 `pbDefaulted`  
 フラグへのポインターがの SE_DACL_DEFAULTED フラグの値に設定、 **SECURITY_DESCRIPTOR_CONTROL**構造随意**ACL**のセキュリティ記述子が存在します。 このフラグが true の場合、随意**ACL** false の場合、既定の機構によって取得された随意**ACL**ユーザーによって明示的に指定されました。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、false、失敗した場合に true を返します。  
  
##  <a name="getgroup"></a>CSecurityDesc::GetGroup  
 セキュリティ記述子からプライマリ グループの情報を取得します。  
  
```
bool GetGroup(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSid`  
 ポインター、 [CSid](../../atl/reference/csid-class.md) (セキュリティ識別子)、CDacl に格納されているグループのコピーを受信します。  
  
 `pbDefaulted`  
 フラグへのポインターがであることを示しますフラグの値に設定、 **SECURITY_DESCRIPTOR_CONTROL**メソッドが戻るときに構成します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、false、失敗した場合に true を返します。  
  
##  <a name="getowner"></a>CSecurityDesc::GetOwner  
 セキュリティ記述子から所有者の情報を取得します。  
  
```
bool GetOwner(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSid`  
 ポインター、 [CSid](../../atl/reference/csid-class.md) (セキュリティ識別子)、CDacl に格納されているグループのコピーを受信します。  
  
 `pbDefaulted`  
 フラグへのポインターがの SE_OWNER_DEFAULTED フラグの値に設定、 **SECURITY_DESCRIPTOR_CONTROL**メソッドが戻るときに構成します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、false、失敗した場合に true を返します。  
  
##  <a name="getpsecurity_descriptor"></a>CSecurityDesc::GetPSECURITY_DESCRIPTOR  
 ポインターを返す、 **SECURITY_DESCRIPTOR**構造体。  
  
```
const SECURITY_DESCRIPTOR* GetPSECURITY_DESCRIPTOR() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 ポインターを返す、 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)構造体。  
  
##  <a name="getsacl"></a>CSecurityDesc::GetSacl  
 セキュリティ記述子からシステム アクセス制御リスト (SACL) 情報を取得します。  
  
```
bool GetSacl(
    CSacl* pSacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSacl`  
 ポインター、`CSacl`セキュリティ記述子の SACL のコピーを格納する構造体。 システムが、 **ACL**メソッドのセットが存在する`pSacl`セキュリティ記述子のシステムのアドレスに**ACL**します。 システムが、 **ACL**が存在しない値は格納されません。  
  
 `pbPresent`  
 メソッドは、システムの存在を確認する設定フラグへのポインター **ACL**で指定されたセキュリティ記述子。 セキュリティ記述子には、システムが含まれている場合**ACL**、このパラメーターの設定を true にします。 セキュリティ記述子には、システムが含まれていない場合**ACL**、このパラメーターが false に設定します。  
  
 `pbDefaulted`  
 フラグへのポインターがの SE_SACL_DEFAULTED フラグの値に設定、 **SECURITY_DESCRIPTOR_CONTROL**システムが、構造体**ACL**のセキュリティ記述子が存在します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、false、失敗した場合に true を返します。  
  
##  <a name="isdaclautoinherited"></a>CSecurityDesc::IsDaclAutoInherited  
 随意アクセス制御リスト (DACL) が自動伝達をサポートするために構成されているかどうかを判断します。  
  
```
bool IsDaclAutoInherited() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子には、既存の子オブジェクトに継承可能なアクセス制御エントリ (Ace) の自動適用をサポートするために構成されている DACL が含まれている場合に true を返します。 それ以外の場合は、false を返します。  
  
### <a name="remarks"></a>コメント  
 オブジェクトとの既存の子オブジェクトの自動的な継承アルゴリズムを実行するときに、このビットが設定されます。  
  
##  <a name="isdacldefaulted"></a>CSecurityDesc::IsDaclDefaulted  
 セキュリティ記述子が既定の随意アクセス制御リスト (DACL) に設定されているかどうかを判断します。  
  
```
bool IsDaclDefaulted() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子が含まれる場合、既定値の DACL の場合、false の場合それ以外の場合は、true を返します。  
  
### <a name="remarks"></a>コメント  
 このフラグは、システムがアクセス制御エントリ (ACE) の継承の DACL を処理する方法に影響します。 たとえば、オブジェクトの作成者が DACL を指定しない場合、オブジェクトは、作成者のアクセス トークンから既定の DACL を受け取ります。 SE_DACL_PRESENT フラグが設定されていない場合、このフラグは無視されます。  
  
 このフラグは、オブジェクトの最終的な DACL を計算する方法を決定するために使用し、セキュリティ保護可能なオブジェクトのセキュリティ記述子のコントロールに物理的に格納されていません。  
  
 このフラグを設定するには、使用、 [CSecurityDesc::SetDacl](#setdacl)メソッドです。  
  
##  <a name="isdaclpresent"></a>CSecurityDesc::IsDaclPresent  
 セキュリティ記述子に随意アクセス制御リスト (DACL) が含まれているかどうかを判断します。  
  
```
bool IsDaclPresent() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子が含まれる場合、DACL の場合、false の場合それ以外の場合は true を返します。  
  
### <a name="remarks"></a>コメント  
 このフラグが設定されていない場合、またはこのフラグが設定され、DACL が NULL の場合、セキュリティ記述子は、すべてのユーザーへのフル アクセスを許可します。  
  
 このフラグは、セキュリティ記述子がセキュリティ保護可能なオブジェクトに関連付けられるまで、呼び出し元が指定されたセキュリティ情報を保持するために使用されます。 セキュリティ記述子は、セキュリティ保護可能なオブジェクトに関連付けられたは、セキュリティ記述子のコントロールに SE_DACL_PRESENT フラグが常に設定します。  
  
 このフラグを設定するには、使用、 [CSecurityDesc::SetDacl](#setdacl)メソッドです。  
  
##  <a name="isdaclprotected"></a>CSecurityDesc::IsDaclProtected  
 変更を防ぐ随意アクセス制御リスト (DACL) が構成されているかどうかを判断します。  
  
```
bool IsDaclProtected() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 DACL をセキュリティ記述子が継承可能なアクセス制御エントリ (Ace) によって変更されることを防ぐために構成されている場合に true を返します。 それ以外の場合は、false を返します。  
  
### <a name="remarks"></a>コメント  
 このフラグを設定するには、使用、 [CSecurityDesc::SetDacl](#setdacl)メソッドです。  
  
 このメソッドはのみ意味のある Windows 2000 またはそれ以降、Windows 2000 のみが継承可能な Ace の自動適用をサポートしています。  
  
##  <a name="isgroupdefaulted"></a>CSecurityDesc::IsGroupDefaulted  
 既定で設定されたセキュリティ記述子のグループ セキュリティ識別子 (SID) を決定します。  
  
```
bool IsGroupDefaulted() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 True を返しますが、セキュリティ記述子の元のプロバイダーではなく、既定のメカニズムでは、指定のセキュリティ記述子の場合グループ SID。 それ以外の場合は、false を返します。  
  
### <a name="remarks"></a>コメント  
 このフラグを設定するには、使用、 [CSecurityDesc::SetGroup](#setgroup)メソッドです。  
  
##  <a name="isownerdefaulted"></a>CSecurityDesc::IsOwnerDefaulted  
 既定で設定されたセキュリティ記述子の所有者セキュリティ識別子 (SID) を決定します。  
  
```
bool IsOwnerDefaulted() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子の元のプロバイダーではなく、既定の機構は、セキュリティ記述子の所有者の SID を指定する場合は、true を返します。 それ以外の場合は、false を返します。  
  
### <a name="remarks"></a>コメント  
 このフラグを設定するには、使用、 [CSecurityDesc::SetOwner](#setowner)メソッドです。  
  
##  <a name="issaclautoinherited"></a>CSecurityDesc::IsSaclAutoInherited  
 自動適用をサポートするために、システム アクセス制御リスト (SACL) が構成されているかどうかを判断します。  
  
```
bool IsSaclAutoInherited() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子には、既存の子オブジェクトに継承可能なアクセス制御エントリ (Ace) の自動適用をサポートするために構成されている SACL が含まれている場合に true を返します。 それ以外の場合は、false を返します。  
  
### <a name="remarks"></a>コメント  
 オブジェクトとの既存の子オブジェクトの自動的な継承アルゴリズムを実行するときに、このビットが設定されます。  
  
##  <a name="issacldefaulted"></a>CSecurityDesc::IsSaclDefaulted  
 セキュリティ記述子が既定のシステム アクセス制御リスト (SACL) に設定されているかどうかを判断します。  
  
```
bool IsSaclDefaulted() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子が含まれる場合、既定の SACL、false の場合それ以外の場合は、true を返します。  
  
### <a name="remarks"></a>コメント  
 このフラグは、システムがアクセス制御エントリ (ACE) の継承の SACL を処理する方法に影響します。 SE_SACL_PRESENT フラグが設定されていない場合、このフラグは無視されます。  
  
 このフラグを設定するには、使用、 [CSecurityDesc::SetSacl](#setsacl)メソッドです。  
  
##  <a name="issaclpresent"></a>CSecurityDesc::IsSaclPresent  
 セキュリティ記述子に、システム アクセス制御リスト (SACL) が含まれているかどうかを判断します。  
  
```
bool IsSaclPresent() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子が含まれる場合、SACL false それ以外の場合は true を返します。  
  
### <a name="remarks"></a>コメント  
 このフラグを設定するには、使用、 [CSecurityDesc::SetSacl](#setsacl)メソッドです。  
  
##  <a name="issaclprotected"></a>CSecurityDesc::IsSaclProtected  
 変更を防ぐシステム アクセス制御リスト (SACL) が構成されているかどうかを判断します。  
  
```
bool IsSaclProtected() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子が継承可能なアクセス制御エントリ (Ace) によって変更されることを防ぐため、SACL が構成されている場合に true を返します。 それ以外の場合は、false を返します。  
  
### <a name="remarks"></a>コメント  
 このフラグを設定するには、使用、 [CSecurityDesc::SetSacl](#setsacl)メソッドです。  
  
 このメソッドはのみ意味のある Windows 2000 またはそれ以降、Windows 2000 のみが継承可能な Ace の自動適用をサポートしています。  
  
##  <a name="isselfrelative"></a>CSecurityDesc::IsSelfRelative  
 セキュリティ記述子が自己相対形式のかどうかを判断します。  
  
```
bool IsSelfRelative() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 連続するメモリ ブロックのすべてのセキュリティ情報とセキュリティ記述子には自己相対形式の場合は true を返します。 セキュリティ記述子には絶対形式の場合は false を返します。 詳細については、次を参照してください。[絶対パスと Self-Relative ムタ糺揵](http://msdn.microsoft.com/library/windows/desktop/aa374807)します。  
  
##  <a name="makeabsolute"></a>CSecurityDesc::MakeAbsolute  
 セキュリティ記述子を絶対形式に変換するには、このメソッドを呼び出します。  
  
```
bool MakeAbsolute() throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、false それ以外の場合は true を返します。  
  
### <a name="remarks"></a>コメント  
 絶対形式のセキュリティ記述子には、情報自体ではなく、ユーザーが含まれる情報へのポインターが含まれています。 自己相対形式のセキュリティ記述子には、連続するメモリ ブロック内の情報が含まれています。 自己相対セキュリティ記述子で、 **SECURITY_DESCRIPTOR**構造は常に、情報を起動しますが、セキュリティ記述子の他のコンポーネントは任意の順序で構造に従うことができます。 メモリ アドレスを使用する代わりに、自己相対セキュリティ記述子のコンポーネントは、セキュリティ記述子の先頭からのオフセットによって識別されます。 この形式は、セキュリティ記述子をディスクに保存または通信プロトコルを使用して送信される必要がある場合に便利です。 詳細については、次を参照してください。[絶対パスと Self-Relative ムタ糺揵](http://msdn.microsoft.com/library/windows/desktop/aa374807)します。  
  
##  <a name="makeselfrelative"></a>CSecurityDesc::MakeSelfRelative  
 セキュリティ記述子を自己相対形式に変換するには、このメソッドを呼び出します。  
  
```
bool MakeSelfRelative() throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、false それ以外の場合は true を返します。  
  
### <a name="remarks"></a>コメント  
 絶対形式のセキュリティ記述子には、情報自体が含まれているのではなく、それに含まれる情報へのポインターが含まれています。 自己相対形式のセキュリティ記述子には、連続するメモリ ブロック内の情報が含まれています。 自己相対セキュリティ記述子で、 **SECURITY_DESCRIPTOR**構造は常に、情報を起動しますが、セキュリティ記述子の他のコンポーネントは任意の順序で構造に従うことができます。 メモリ アドレスを使用する代わりに、セキュリティ記述子のコンポーネントは、セキュリティ記述子の先頭からのオフセットによって識別されます。 この形式は、セキュリティ記述子をディスクに保存または通信プロトコルを使用して送信される必要がある場合に便利です。 詳細については、次を参照してください。[絶対パスと Self-Relative ムタ糺揵](http://msdn.microsoft.com/library/windows/desktop/aa374807)します。  
  
##  <a name="operator_eq"></a>CSecurityDesc::operator =  
 代入演算子。  
  
```
CSecurityDesc& operator= (const SECURITY_DESCRIPTOR& rhs) throw(...);  
CSecurityDesc& operator= (const CSecurityDesc& rhs) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 **SECURITY_DESCRIPTOR**構造または`CSecurityDesc`オブジェクトに割り当てる、`CSecurityDesc`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 取得、更新された`CSecurityDesc`オブジェクトです。  
  
##  <a name="operator_const_security_descriptor__star"></a>CSecurityDesc::operator const SECURITY_DESCRIPTOR *  
 値へのポインターをキャスト、 **SECURITY_DESCRIPTOR**構造体。  
  
```  
operator const SECURITY_DESCRIPTOR *() const throw();
```  
  
##  <a name="setcontrol"></a>CSecurityDesc::SetControl  
 セキュリティ記述子の制御ビットを設定します。  
  
```
bool SetControl(
    SECURITY_DESCRIPTOR_CONTROL ControlBitsOfInterest, 
    SECURITY_DESCRIPTOR_CONTROL ControlBitsToSet) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `ControlBitsOfInterest`  
 A **SECURITY_DESCRIPTOR_CONTROL**マスクを設定する制御ビットを示します。 設定できるフラグの一覧は、次を参照してください。 [SetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx)します。  
  
 `ControlBitsToSe`t  
 `SECURITY_DESCRIPTOR_CONTROL` マスクによって指定される制御ビットの新しい値を示す `ControlBitsOfInterest` マスク。 このパラメーターには、`ControlBitsOfInterest` パラメーターの項に記載されているフラグの組み合わせを使用できます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、使用可能な Windows 2000 でのみと、後でなさ[SetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx)します。  
  
##  <a name="setdacl"></a>CSecurityDesc::SetDacl  
 随意アクセス制御リスト (DACL) で情報を設定します。 既に DACL が表示されている、セキュリティ記述子で置き換えられます。  
  
```
inline void SetDacl(  
    bool bPresent = true,
    bool bDefaulted = false) throw(...);

inline void SetDacl(  
    const CDacl& Dacl,
    bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *Dacl*  
 参照、`CDacl`のセキュリティ記述子の DACL を指定するオブジェクト。 このパラメーターには、NULL は指定できません。 セキュリティ記述子には、NULL DACL を設定するでメソッドの最初の形式を使用する`bPresent`を false に設定します。  
  
 `bPresent`  
 セキュリティ記述子の DACL の存在を示すフラグを指定します。 このパラメーターが true の場合、メソッドには、SE_DACL_PRESENT フラグを設定、 **SECURITY_DESCRIPTOR_CONTROL**構造体の値を使用して、 *Dacl*と`bDefaulted`パラメーター。 False の場合、メソッドは SE_DACL_PRESENT フラグをクリアし、`bDefaulted`は無視されます。  
  
 `bDefaulted`  
 DACL のソースを示すフラグを指定します。 このフラグが true の場合、DACL は既定の機構によって取得されました。 False の場合、DACL がユーザーが明示的に指定されています。 メソッドの SE_DACL_DEFAULTED フラグでこの値を格納する、 **SECURITY_DESCRIPTOR_CONTROL**構造体。 このパラメーターが指定されていない場合は、SE_DACL_DEFAULTED フラグがクリアされます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 空と存在しない DACL の重要な違いがあります。 DACL が空の場合は、アクセス制御エントリが含まれていないとへのアクセス権明示的に与えられていません。 その結果、オブジェクトへのアクセスが暗黙的に拒否されます。 その一方で、オブジェクトに DACL がしない場合は、保護は、オブジェクトに割り当てられませんし、アクセス要求が許可されます。  
  
##  <a name="setgroup"></a>CSecurityDesc::SetGroup  
 既にあるすべてのプライマリ グループ情報を交換絶対形式のセキュリティ記述子のプライマリ グループの情報を設定します。  
  
```
bool SetGroup(const CSid& Sid, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `Sid`  
 参照、 [CSid](../../atl/reference/csid-class.md)セキュリティ記述子の新しいプライマリ グループのオブジェクト。 このパラメーターには、NULL は指定できません。 セキュリティ記述子は、DACL または SACL を持っていないと設定されていることができますが、これらも、グループと、所有者が必要は NULL SID (ある特別な意味を持つ組み込み SID)。  
  
 `bDefaulted`  
 プライマリ グループの情報が既定のメカニズムから派生したかどうかを示します。 この値は true、それは既定の情報およびメソッドであることを示しますフラグとしてこの値を格納する場合、 **SECURITY_DESCRIPTOR_CONTROL**構造体。 このパラメーターが&0; の場合は、SE_GROUP_DEFAULTED フラグがクリアされます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="setowner"></a>CSecurityDesc::SetOwner  
 絶対形式のセキュリティ記述子の所有者の情報を設定します。 所有者の情報が既に組み込まれているが置き換えられます。  
  
```
bool SetOwner(const CSid& Sid, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `Sid`  
 [CSid](../../atl/reference/csid-class.md)セキュリティ記述子の新しいプライマリ所有者のオブジェクト。 このパラメーターには、NULL は指定できません。  
  
 `bDefaulted`  
 所有者情報は、既定の機構から派生するかどうかを示します。 この値が true の場合は、既定の情報です。 メソッドで SE_OWNER_DEFAULTED フラグとしてこの値を格納する、 **SECURITY_DESCRIPTOR_CONTROL**構造体。 このパラメーターが&0; の場合は、SE_OWNER_DEFAULTED フラグがクリアされます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="setsacl"></a>CSecurityDesc::SetSacl  
 システム アクセス制御リスト (SACL) の情報を設定します。 既に SACL が表示されている、セキュリティ記述子で置き換えられます。  
  
```
bool SetSacl(const CSacl& Sacl, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *Sacl*  
 ポインター、`CSacl`のセキュリティ記述子の SACL を指定するオブジェクト。 このパラメーターは、NULL は指定できません、CSacl オブジェクトである必要があります。 Dacl とは異なりは NULL と空の SACL の違い SACL オブジェクトのみの監査情報のアクセス権を指定しないと、  
  
 `bDefaulted`  
 SACL のソースを示すフラグを指定します。 このフラグが true の場合、SACL は既定の機構によって取得されました。 False の場合、ユーザーが SACL を明示的に指定されています。 メソッドの SE_SACL_DEFAULTED フラグでこの値を格納する、 **SECURITY_DESCRIPTOR_CONTROL**構造体。 このパラメーターが指定されていない場合は、SE_SACL_DEFAULTED フラグがクリアされます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="tostring"></a>CSecurityDesc::ToString  
 セキュリティ記述子を文字列形式に変換します。  
  
```
bool ToString(
    CString* pstr, SECURITY_INFORMATION si = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstr`  
 お届けする null で終わる文字列へのポインター、[文字列形式のセキュリティ記述子](http://msdn.microsoft.com/library/windows/desktop/aa379570)します。  
  
 `si`  
 出力文字列に含めるセキュリティ記述子のコンポーネントを示すために SECURITY_INFORMATION ビット フラグの組み合わせを指定します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 セキュリティ記述子は、文字列の形式では後より簡単に保存または転送します。 使用して、`CSecurityDesc::FromString`セキュリティ記述子に、文字列に変換します。  
  
 `si`パラメーターは、次の SECURITY_INFORMATION フラグを含めることができます。  
  
|値|説明|  
|-----------|-------------|  
|OWNER_SECURITY_INFORMATION|所有者を含めます。|  
|GROUP_SECURITY_INFORMATION|プライマリ グループを含めます。|  
|DACL_SECURITY_INFORMATION|DACL が含まれます。|  
|SACL_SECURITY_INFORMATION|SACL が含まれます。|  
  
 DACL は、NULL、入力セキュリティ記述子に SE_DACL_PRESENT の制御ビットが設定されている場合は、メソッドは失敗します。  
  
 DACL は、NULL 入力セキュリティ記述子に SE_DACL_PRESENT の制御ビットが設定されていない場合は、結果として得られるセキュリティ記述子文字列には d: コンポーネントはありません。 参照してください[セキュリティ記述子の文字列形式](http://msdn.microsoft.com/library/windows/desktop/aa379570)詳細です。  
  
 このメソッドは使用可能な Windows 2000 以降を呼び出すよう[convertstringsecuritydescriptortosecuritydescriptor が](http://msdn.microsoft.com/library/windows/desktop/aa376401)です。  
  
## <a name="see-also"></a>関連項目  
 [セキュリティのサンプル](../../visual-cpp-samples.md)   
 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)

