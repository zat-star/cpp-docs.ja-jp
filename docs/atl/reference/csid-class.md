---
title: "CSid クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSid
- ATL::CSid
- ATL.CSid
dev_langs:
- C++
helpviewer_keywords:
- CSid class
ms.assetid: be58b7ca-5958-49c3-a833-ca341aaaf753
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
ms.openlocfilehash: ceb0ab95d18e1336584eab45bc00ce769efd7384
ms.lasthandoff: 02/24/2017

---
# <a name="csid-class"></a>CSid クラス
このクラスは、用のラッパー、 `SID` (セキュリティ識別子) 構造体。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CSid
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CSid::CSidArray](#csidarray)|`CSid` オブジェクトの配列。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSid::CSid](#csid)|コンストラクターです。|  
|[CSid:: ~ CSid](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSid::AccountName](#accountname)|関連付けられているアカウントの名前を返す、`CSid`オブジェクトです。|  
|[CSid::Domain](#domain)|関連付けられているドメインの名前を返す、`CSid`オブジェクトです。|  
|[CSid::EqualPrefix](#equalprefix)|テスト`SID`等しいかどうか (セキュリティ識別子) のプレフィックス。|  
|[CSid::GetLength](#getlength)|長さを返す、`CSid`オブジェクトです。|  
|[CSid::GetPSID](#getpsid)|ポインターを返す、`SID`構造体。|  
|[CSid::GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|ポインターを返す、 **SID_IDENTIFIER_AUTHORITY**構造体。|  
|[CSid::GetSubAuthority](#getsubauthority)|指定された副機関を返す、 **SID**構造体。|  
|[から](#getsubauthoritycount)|副機関の数を返します。|  
|[CSid::IsValid](#isvalid)|テスト、`CSid`の有効性のオブジェクト。|  
|[CSid::LoadAccount](#loadaccount)|更新プログラム、`CSid`オブジェクトが指定されたアカウント名とドメイン、または既存の`SID`構造体。|  
|[CSid::Sid](#sid)|ID 文字列を返します。|  
|[CSid::SidNameUse](#sidnameuse)|状態の説明を返す、`CSid`オブジェクトです。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 =](#operator_eq)|代入演算子。|  
|[演算子の const SID *](#operator_const_sid__star)|キャスト、`CSid`オブジェクトへのポインターを`SID`構造体。|  
  
### <a name="global-operators"></a>グローバル演算子  
  
|||  
|-|-|  
|[演算子 = =](#operator_eq_eq)|2 つのセキュリティ記述子オブジェクトの等価性をテストします。|  
|[operator! =](#operator_neq)|2 つのセキュリティ記述子オブジェクトの非等値のテストします。|  
|[演算子\<](#operator_lt_)|2 つのセキュリティ記述子オブジェクトの相対値を比較します。|  
|[演算子 >](#operator_gt_)|2 つのセキュリティ記述子オブジェクトの相対値を比較します。|  
|[演算子\<=](#operator_lt__eq)|2 つのセキュリティ記述子オブジェクトの相対値を比較します。|  
|[演算子 > =](#operator_gt__eq)|2 つのセキュリティ記述子オブジェクトの相対値を比較します。|  
  
## <a name="remarks"></a>コメント  
 `SID`構造は、可変長構造をユーザーまたはグループを一意に識別するために使用します。  
  
 アプリケーションは変更しないで、`SID`構造に直接が、代わりには、このラッパー クラスにメソッドを使用します。 関連項目[AtlGetOwnerSid](http://msdn.microsoft.com/library/0e3a2606-74b8-4412-9803-bb437e22da85)、 [AtlSetGroupSid](http://msdn.microsoft.com/library/83531d32-11ab-4a68-a3c6-1bfa54ab8dfa)、 [AtlGetGroupSid](http://msdn.microsoft.com/library/8e7ec6b9-15c8-4a8a-977e-1e4c853d0be7)、および[AtlSetOwnerSid](http://msdn.microsoft.com/library/3a8abb76-1d2c-465d-a5e8-62a12a3c37f3)します。  
  
 Windows のアクセス制御モデルの概要については、次を参照してください。[アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h  
  
##  <a name="a-nameaccountnamea--csidaccountname"></a><a name="accountname"></a>CSid::AccountName  
 関連付けられているアカウントの名前を返す、`CSid`オブジェクトです。  
  
```
LPCTSTR AccountName() const throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 返します。、`LPCTSTR`アカウントの名前をポイントします。  
  
### <a name="remarks"></a>コメント  
 このメソッドが、指定した名前を検索しようとしています。 `SID` (セキュリティ識別子)。 詳細については、次を参照してください。 [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166)します。  
  
 アカウント名がない場合、`SID`を取れる`AccountName`空の文字列を返します。 これは、ネットワークのタイムアウトが原因でこのメソッドが名前を検索する場合に発生します。 対応するアカウント名がない、ログオンなどのセキュリティ識別子の場合にも発生`SID`ログオン セッションを識別します。  
  
##  <a name="a-namecsida--csidcsid"></a><a name="csid"></a>CSid::CSid  
 コンストラクターです。  
  
```
CSid() throw();
CSid(const SID& rhs) throw(...);
CSid(const CSid& rhs) throw(...);

CSid(
    const SID_IDENTIFIER_AUTHORITY& IdentifierAuthority,
    BYTE nSubAuthorityCount,
    ...) throw(...);

explicit CSid(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

explicit CSid(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 既存の`CSid`オブジェクトまたは`SID`(セキュリティ識別子) 構造体。  
  
 *IdentifierAuthority*  
 証明機関。  
  
 *nSubAuthorityCount*  
 副機関の数。  
  
 `pszAccountName`  
 アカウント名。  
  
 `pszSystem`  
 システム名。 この文字列には、リモート コンピューターの名前を使用できます。 この文字列が NULL の場合は、代わりにローカル システムが使用されます。  
  
 `pSid`  
 ポインター、`SID`構造体。  
  
### <a name="remarks"></a>コメント  
 コンス トラクターは、`CSid`内部データ メンバーに設定されているオブジェクト*SidTypeInvalid*、または既存の設定をコピーして`CSid`、 `SID`、または既存のアカウントです。  
  
 コンス トラクターが初期化に失敗した場合にスローされます、 [CAtlException クラス](../../atl/reference/catlexception-class.md)します。  
  
##  <a name="a-namedtora--csidcsid"></a><a name="dtor"></a>CSid:: ~ CSid  
 デストラクターです。  
  
```
virtual ~CSid() throw();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターは、オブジェクトで取得したリソースを解放します。  
  
##  <a name="a-namecsidarraya--csidcsidarray"></a><a name="csidarray"></a>CSid::CSidArray  
 配列[CSid](../../atl/reference/csid-class.md)オブジェクトです。  
  
```
typedef CAtlArray<CSid> CSidArray;
```  
  
### <a name="remarks"></a>コメント  
 この typedef では、ACL (アクセス制御リスト) からのセキュリティ識別子を取得するために使用する配列の型を指定します。 参照してください[CAcl::GetAclEntries](../../atl/reference/cacl-class.md#getaclentries)します。  
  
##  <a name="a-namedomaina--csiddomain"></a><a name="domain"></a>CSid::Domain  
 関連付けられているドメインの名前を返す、`CSid`オブジェクトです。  
  
```
LPCTSTR Domain() const throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 返します。、`LPCTSTR`ドメインをポイントします。  
  
### <a name="remarks"></a>コメント  
 このメソッドが、指定した名前を検索しようとしています。 `SID` (セキュリティ識別子)。 詳細については、次を参照してください。 [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166)します。  
  
 アカウント名がない場合、`SID`を取れる**ドメイン**空の文字列としてドメインを返します。 これは、ネットワークのタイムアウトが原因でこのメソッドが名前を検索する場合に発生します。 対応するアカウント名がない、ログオンなどのセキュリティ識別子の場合にも発生`SID`ログオン セッションを識別します。  
  
##  <a name="a-nameequalprefixa--csidequalprefix"></a><a name="equalprefix"></a>CSid::EqualPrefix  
 テスト`SID`等しいかどうか (セキュリティ識別子) のプレフィックス。  
  
```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 `SID` (セキュリティ識別子) 構造体または`CSid`と比較するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**成功した場合、 **false**失敗します。  
  
### <a name="remarks"></a>コメント  
 参照してください[EqualPrefixSid](http://msdn.microsoft.com/library/windows/desktop/aa446621)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]詳細です。  
  
##  <a name="a-namegetlengtha--csidgetlength"></a><a name="getlength"></a>CSid::GetLength  
 長さを返す、`CSid`オブジェクトです。  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 長さのバイト数で返します、`CSid`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 場合、`CSid`構造が有効でない戻り値は未定義です。 呼び出しの前に`GetLength`を使用して、 [CSid::IsValid](#isvalid)いることを確認するメンバー関数を`CSid`が有効です。  
  
> [!NOTE]
>  デバッグ ビルドの場合、関数のアサートが発生する、`CSid`オブジェクトが無効です。  
  
##  <a name="a-namegetpsida--csidgetpsid"></a><a name="getpsid"></a>CSid::GetPSID  
 ポインターを返す、 `SID` (セキュリティ識別子) 構造体。  
  
```
const SID* GetPSID() const throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 アドレスを返す、`CSid`オブジェクトの基になる`SID`構造体。  
  
##  <a name="a-namegetpsididentifierauthoritya--csidgetpsididentifierauthority"></a><a name="getpsid_identifier_authority"></a>CSid::GetPSID_IDENTIFIER_AUTHORITY  
 ポインターを返す、 **SID_IDENTIFIER_AUTHORITY**構造体。  
  
```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 アドレスが返される、メソッドが成功した場合、 **SID_IDENTIFIER_AUTHORITY**構造体。 失敗した場合、戻り値は未定義です。 場合に、エラーが発生する可能性があります、`CSid`オブジェクトが有効でない場合、 [CSid::IsValid](#isvalid)メソッドが返す**false**します。 関数`GetLastError`拡張エラー情報を呼び出すことができます。  
  
> [!NOTE]
>  デバッグ ビルドの場合、関数のアサートが発生する、`CSid`オブジェクトが無効です。  
  
##  <a name="a-namegetsubauthoritya--csidgetsubauthority"></a><a name="getsubauthority"></a>CSid::GetSubAuthority  
 指定された副機関を返す、 `SID` (セキュリティ識別子) 構造体。  
  
```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *nSubAuthority*  
 副機関。  
  
### <a name="return-value"></a>戻り値  
 によって参照される副機関を返す*nSubAuthority します。* 副機関値は、相対識別子 (RID) です。  
  
### <a name="remarks"></a>コメント  
 *NSubAuthority*メソッドは副機関配列の要素を識別するインデックス値を指定します。 メソッドは、この値を検証テストを実行しません。 アプリケーションが呼び出すことができます[から](#getsubauthoritycount)値の許容範囲を検出します。  
  
> [!NOTE]
>  デバッグ ビルドの場合、関数のアサートが発生する、`CSid`オブジェクトが無効です。  
  
##  <a name="a-namegetsubauthoritycounta--csidgetsubauthoritycount"></a><a name="getsubauthoritycount"></a>から  
 副機関の数を返します。  
  
```
UCHAR GetSubAuthorityCount() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、副機関の数を返します。  
  
 メソッドが失敗した場合、戻り値は未定義です。 メソッドは失敗、`CSid`オブジェクトが無効です。 拡張されたエラー情報を取得するには、`GetLastError` を呼び出します。  
  
> [!NOTE]
>  デバッグ ビルドの場合、関数のアサートが発生する、`CSid`オブジェクトが無効です。  
  
##  <a name="a-nameisvalida--csidisvalid"></a><a name="isvalid"></a>CSid::IsValid  
 テスト、`CSid`の有効性のオブジェクト。  
  
```
bool IsValid() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**場合、`CSid`オブジェクトが有効で**false**かどうか。 このメソッドの拡張エラー情報はありません。呼び出す必要はありません`GetLastError`します。  
  
### <a name="remarks"></a>コメント  
 `IsValid`メソッドは、検証、`CSid`リビジョン番号が不明の範囲内であると、副機関の数が最大値より小さいことを確認することによってオブジェクトです。  
  
##  <a name="a-nameloadaccounta--csidloadaccount"></a><a name="loadaccount"></a>CSid::LoadAccount  
 指定されたアカウント名とドメイン、または既存の SID (セキュリティ識別子) 構造体で、`CSid` オブジェクトを更新します。  
  
```
bool LoadAccount(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

bool LoadAccount(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszAccountName`  
 アカウント名。  
  
 `pszSystem`  
 システム名。 この文字列には、リモート コンピューターの名前を使用できます。 この文字列が NULL の場合は、代わりにローカル システムが使用されます。  
  
 `pSid`  
 ポインター、 [SID](http://msdn.microsoft.com/library/windows/desktop/aa379594\(v=vs.85\).aspx)構造体。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**成功した場合、 **false**失敗します。 拡張されたエラー情報を取得するには、`GetLastError` を呼び出します。  
  
### <a name="remarks"></a>コメント  
 `LoadAccount` は、指定された名前でセキュリティ識別子の検索を試行します。 参照してください[LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166\(v=vs.85\).aspx)詳細です。  
  
##  <a name="a-nameoperatoreqa--csidoperator-"></a><a name="operator_eq"></a>CSid::operator =  
 代入演算子。  
  
```
CSid& operator= (const CSid& rhs) throw(...);  
CSid& operator= (const SID& rhs) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 `SID` (セキュリティ識別子) または`CSid`に割り当てる、`CSid`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 更新されたへの参照を返します`CSid`オブジェクトです。  
  
##  <a name="a-nameoperatoreqeqa--csidoperator-"></a><a name="operator_eq_eq"></a>CSid::operator = =  
 2 つのセキュリティ記述子オブジェクトの等価性をテストします。  
  
```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 `SID` (セキュリティ識別子) または`CSid`の左側に表示される、演算子 = = です。  
  
 `rhs`  
 `SID` (セキュリティ識別子) または`CSid`の右側に表示される、演算子 = = です。  
  
### <a name="return-value"></a>戻り値  
 **true**セキュリティ記述子が等しい場合**false**します。  
  
##  <a name="a-nameoperatorneqa--csidoperator-"></a><a name="operator_neq"></a>CSid::operator! =  
 2 つのセキュリティ記述子オブジェクトの非等値をテストします。  
  
```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 `SID` (セキュリティ識別子) または`CSid`の左側に表示される、! = 演算子。  
  
 `rhs`  
 `SID` (セキュリティ識別子) または`CSid`の右側に表示される、! = 演算子。  
  
### <a name="return-value"></a>戻り値  
 **true**セキュリティ記述子が異なる場合は、それ以外の場合**false**します。  
  
##  <a name="a-nameoperatorlta--csidoperator-lt"></a><a name="operator_lt"></a>CSid::operator&lt;  
 2 つのセキュリティ記述子オブジェクトの相対値を比較します。  
  
```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 `SID` (セキュリティ識別子) または`CSid`の左側に表示される、! = 演算子。  
  
 `rhs`  
 `SID` (セキュリティ識別子) または`CSid`の右側に表示される、! = 演算子。  
  
### <a name="return-value"></a>戻り値  
 **true**場合`lhs`がより小さい`rhs`、それ以外の場合**false**します。  
  
##  <a name="a-nameoperatorlteqa--csidoperator-lt"></a><a name="operator_lt__eq"></a>CSid::operator&lt;=  
 2 つのセキュリティ記述子オブジェクトの相対値を比較します。  
  
```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 `SID` (セキュリティ識別子) または`CSid`の左側に表示される、! = 演算子。  
  
 `rhs`  
 `SID` (セキュリティ識別子) または`CSid`の右側に表示される、! = 演算子。  
  
### <a name="return-value"></a>戻り値  
 **true**場合`lhs`と同じかそれよりも少ない`rhs`、それ以外の場合**false**します。  
  
##  <a name="a-nameoperatorgta--csidoperator-gt"></a><a name="operator_gt"></a>CSid::operator&gt;  
 2 つのセキュリティ記述子オブジェクトの相対値を比較します。  
  
```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 `SID` (セキュリティ識別子) または`CSid`の左側に表示される、! = 演算子。  
  
 `rhs`  
 `SID` (セキュリティ識別子) または`CSid`の右側に表示される、! = 演算子。  
  
### <a name="return-value"></a>戻り値  
 **true**場合`lhs`よりも大きい`rhs`、それ以外の場合**false**します。  
  
##  <a name="a-nameoperatorgteqa--csidoperator-gt"></a><a name="operator_gt__eq"></a>CSid::operator&gt;=  
 2 つのセキュリティ記述子オブジェクトの相対値を比較します。  
  
```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 `SID` (セキュリティ識別子) または`CSid`の左側に表示される、! = 演算子。  
  
 `rhs`  
 `SID` (セキュリティ識別子) または`CSid`の右側に表示される、! = 演算子。  
  
### <a name="return-value"></a>戻り値  
 **true**場合`lhs`に以上`rhs`、それ以外の場合**false**します。  
  
##  <a name="a-nameoperatorconstsidstara--csidoperator-const-sid-"></a><a name="operator_const_sid__star"></a>CSid::operator const SID *  
 キャスト、`CSid`オブジェクトへのポインターを`SID`(セキュリティ識別子) 構造体。  
  
```  
operator const SID *() const throw(...);
```  
  
### <a name="remarks"></a>コメント  
 アドレスを返す、`SID`構造体。  
  
##  <a name="a-namesida--csidsid"></a><a name="sid"></a>CSid::Sid  
 返します。、`SID`を文字列として (セキュリティ識別子) 構造体。  
  
```
LPCTSTR Sid() const throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 返します。、`SID`表示、ストレージ、または転送に適した形式の文字列と構造が作成されます。 等価[ConvertSidToStringSid](http://msdn.microsoft.com/library/windows/desktop/aa376399)この関数では Windows 2000 で利用可能な以降のみが、以前のオペレーティング システムがエミュレートされるようにします。  
  
##  <a name="a-namesidnameusea--csidsidnameuse"></a><a name="sidnameuse"></a>CSid::SidNameUse  
 状態の説明を返す、`CSid`オブジェクトです。  
  
```
SID_NAME_USE SidNameUse() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 状態を示す値を格納するデータ メンバーの値を返す、`CSid`オブジェクトです。  
  
|値|説明|  
|-----------|-----------------|  
|SidTypeUser|ユーザーを示す`SID`(セキュリティ識別子)。|  
|SidTypeGroup|グループを示す`SID`します。|  
|SidTypeDomain|ドメインを示す`SID`します。|  
|SidTypeAlias|別名を示す`SID`します。|  
|SidTypeWellKnownGroup|示す、`SID`既知のグループにします。|  
|SidTypeDeletedAccount|示す、`SID`削除されたアカウントにします。|  
|SidTypeInvalid|無効なことを示します`SID`します。|  
|SidTypeUnknown|不明なを示す`SID`型です。|  
|SidTypeComputer|示す、`SID`コンピューター用です。|  
  
### <a name="remarks"></a>コメント  
 呼び出す[CSid::LoadAccount](#loadaccount)を更新する、`CSid`オブジェクトを呼び出す前に`SidNameUse`の状態に戻ります。 `SidNameUse`オブジェクトの状態は変更されません (を呼び出すことによって**LookupAccountName**または**LookupAccountSid**)、のみ現在の状態を返しています。  
  
## <a name="see-also"></a>関連項目  
 [セキュリティのサンプル](../../visual-cpp-samples.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)   
 [演算子](../../atl/reference/atl-operators.md)

