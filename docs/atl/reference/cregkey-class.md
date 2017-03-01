---
title: "CRegKey クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRegKey
- ATL::CRegKey
- ATL.CRegKey
dev_langs:
- C++
helpviewer_keywords:
- CRegKey class
- ATL, registry
- registry, deleting values
- registry, writing to
- registry, deleting keys
ms.assetid: 3afce82b-ba2c-4c1a-8404-dc969e1af74b
caps.latest.revision: 25
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
ms.openlocfilehash: d0ab2a2a0c74ed3d6b48297cc052ebbf09bd3291
ms.lasthandoff: 02/24/2017

---
# <a name="cregkey-class"></a>CRegKey クラス
このクラスは、システム レジストリのエントリを操作するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CRegKey
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CRegKey::CRegKey](#cregkey)|コンストラクターです。|  
|[CRegKey:: ~ CRegKey](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRegKey::Attach](#attach)|HKEY をアタッチするには、このメソッドを呼び出す、`CRegKey`オブジェクトを設定して、 [m_hKey](#m_hkey)メンバーを識別するハンドル`hKey`します。|  
|[CRegKey::Close](#close)|解放するには、このメソッドを呼び出して、 [m_hKey](#m_hkey)メンバーを処理し、NULL に設定します。|  
|[CRegKey::Create](#create)|としてのサブキーが存在しない場合は、指定したキーを作成するには、このメソッドを呼び出す`hKeyParent`します。|  
|[CRegKey::DeleteSubKey](#deletesubkey)|指定したキーをレジストリから削除するには、このメソッドを呼び出します。|  
|[CRegKey::DeleteValue](#deletevalue)|値フィールドを削除するには、このメソッドを呼び出す[m_hKey](#m_hkey)します。|  
|[CRegKey::Detach](#detach)|デタッチするには、このメソッドを呼び出して、 [m_hKey](#m_hkey)からのメンバーのハンドル、`CRegKey`オブジェクトし、設定`m_hKey`を NULL にします。|  
|[して](#enumkey)|開いているレジストリ キーのサブキーを列挙するには、このメソッドを呼び出します。|  
|[CRegKey::Flush](#flush)|すべての開いているレジストリ キーの属性をレジストリに書き込むには、このメソッドを呼び出します。|  
|[CRegKey::GetKeySecurity](#getkeysecurity)|開いているレジストリ キーを保護するセキュリティ記述子のコピーを取得するには、このメソッドを呼び出します。|  
|[CRegKey::NotifyChangeKeyValue](#notifychangekeyvalue)|このメソッドでは、属性または開いているレジストリ キーの内容の変更について、呼び出し元に通知します。|  
|[Cregkey::open](#open)|指定したキーを開き、設定するには、このメソッドを呼び出す[m_hKey](#m_hkey)をこのキーのハンドル。|  
|[CRegKey::QueryBinaryValue](#querybinaryvalue)|指定された値の名前のバイナリ データを取得するには、このメソッドを呼び出します。|  
|[CRegKey::QueryDWORDValue](#querydwordvalue)|指定された値の名前の DWORD データを取得するには、このメソッドを呼び出します。|  
|[CRegKey::QueryGUIDValue](#queryguidvalue)|指定された値名の GUID のデータを取得するには、このメソッドを呼び出します。|  
|[CRegKey::QueryMultiStringValue](#querymultistringvalue)|指定された値名の複数文字列のデータを取得するには、このメソッドを呼び出します。|  
|[CRegKey::QueryQWORDValue](#queryqwordvalue)|指定された値名の QWORD データを取得するには、このメソッドを呼び出します。|  
|[CRegKey::QueryStringValue](#querystringvalue)|指定された値名の文字列データを取得するには、このメソッドを呼び出します。|  
|[CRegKey::QueryValue](#queryvalue)|指定した値フィールドのデータを取得するには、このメソッドを呼び出す[m_hKey](#m_hkey)します。 このメソッドの以前のバージョンが現在サポートされていませんしとマークされて**されず**します。|  
|[CRegKey::RecurseDeleteKey](#recursedeletekey)|指定したキーをレジストリから削除し、すべてのサブキーを明示的に削除するには、このメソッドを呼び出します。|  
|[CRegKey::SetBinaryValue](#setbinaryvalue)|レジストリ キーのバイナリ値を設定するには、このメソッドを呼び出します。|  
|[CRegKey::SetDWORDValue](#setdwordvalue)|レジストリ キーの DWORD 値を設定するには、このメソッドを呼び出します。|  
|[CRegKey::SetGUIDValue](#setguidvalue)|レジストリ キーの GUID 値を設定するには、このメソッドを呼び出します。|  
|[CRegKey::SetKeySecurity](#setkeysecurity)|レジストリ キーのセキュリティを設定するには、このメソッドを呼び出します。|  
|[CRegKey::SetKeyValue](#setkeyvalue)|指定したキーの指定した値フィールドにデータを格納するには、このメソッドを呼び出します。|  
|[CRegKey::SetMultiStringValue](#setmultistringvalue)|レジストリ キーの複数文字列の値を設定するには、このメソッドを呼び出します。|  
|[CRegKey::SetQWORDValue](#setqwordvalue)|レジストリ キーの QWORD 値を設定するには、このメソッドを呼び出します。|  
|[CRegKey::SetStringValue](#setstringvalue)|レジストリ キーの文字列値を設定します。|  
|[CRegKey::SetValue](#setvalue)|指定した値フィールドにデータを格納するには、このメソッドを呼び出す[m_hKey](#m_hkey)します。 このメソッドの以前のバージョンが現在サポートされていませんしとマークされて**されず**します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CRegKey::operator HKEY](#operator_hkey)|変換、 `CRegKey` HKEY するオブジェクト。|  
|[CRegKey::operator =](#operator_eq)|代入演算子。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CRegKey::m_hKey](#m_hkey)|関連付けられているレジストリ キーのハンドルを含む、`CRegKey`オブジェクトです。|  
|[CRegKey::m_pTM](#m_ptm)|ポインター`CAtlTransactionManager`オブジェクト|  
  
## <a name="remarks"></a>コメント  
 `CRegKey`作成すると、システム レジストリのキーと値を削除するには、メソッドを提供します。 レジストリには、インストールに固有の一連ソフトウェアのバージョン番号、インストールされているハードウェアや COM オブジェクトの論理/物理マッピングなどのシステム コンポーネントの定義にはが含まれています。  
  
 `CRegKey`特定のコンピューターのシステムのレジストリへのプログラミング インターフェイスを提供します。 たとえば、特定のレジストリ キーを開くを呼び出す`CRegKey::Open`します。 取得したり、データ値を変更したりするには、呼び出す`CRegKey::QueryValue`または`CRegKey::SetValue`、それぞれします。 キーを閉じるを呼び出す`CRegKey::Close`します。  
  
 キーを閉じると、レジストリ データに書き込まれます (フラッシュ) ハード ディスク。 このプロセスは数秒をかかります。 場合は、アプリケーションは、ハード_ディスクにレジストリ データを明示的に記述する必要がありますを呼び出すことができます、 [RegFlushKey](http://msdn.microsoft.com/library/windows/desktop/ms724867) Win32 関数です。 ただし、 **RegFlushKey**多くのシステム リソースを使用し、どうしても必要な場合にのみ呼び出す必要があります。  
  
> [!IMPORTANT]
>  レジストリの場所を指定する、呼び出し元を許可するすべてのメソッドには、信頼できないデータを読み取る可能性があります。 できるようにするメソッドを使用して[RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911)この関数が明示的に NULL 終端の文字列を処理する注意点を考慮する必要があります。 呼び出し元のコードの両方の条件を確認する必要があります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="a-nameattacha--cregkeyattach"></a><a name="attach"></a>CRegKey::Attach  
 HKEY をアタッチするには、このメソッドを呼び出す、`CRegKey`オブジェクトを設定して、 [m_hKey](#m_hkey)メンバーを識別するハンドル`hKey`します。  
  
```
void Attach(HKEY hKey) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hKey`  
 レジストリ キーのハンドル。  
  
### <a name="remarks"></a>コメント  
 **アタッチ**場合はアサート`m_hKey`以外の場合します。  
  
##  <a name="a-nameclosea--cregkeyclose"></a><a name="close"></a>CRegKey::Close  
 解放するには、このメソッドを呼び出して、 [m_hKey](#m_hkey)メンバーを処理し、NULL に設定します。  
  
```
LONG Close() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS; を返しますそれ以外の場合、エラー値を返します。  
  
##  <a name="a-namecreatea--cregkeycreate"></a><a name="create"></a>CRegKey::Create  
 としてのサブキーが存在しない場合は、指定したキーを作成するには、このメソッドを呼び出す`hKeyParent`します。  
  
```
LONG Create(  
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    LPTSTR lpszClass = REG_NONE,
    DWORD dwOptions = REG_OPTION_NON_VOLATILE,
    REGSAM samDesired = KEY_READ | KEY_WRITE,
    LPSECURITY_ATTRIBUTES lpSecAttr = NULL,
    LPDWORD lpdwDisposition = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hKeyParent`  
 オープンするキーのハンドル。  
  
 `lpszKeyName`  
 作成したり開いたりキーの名前を指定します。 この名前のサブキーである必要があります`hKeyParent`します。  
  
 `lpszClass`  
 キーを作成したり開いたりのクラスを指定します。 既定値は、REG_NONE です。  
  
 `dwOptions`  
 キーのオプションです。 既定値は、REG_OPTION_NON_VOLATILE です。 使用可能な値と説明の一覧は、次を参照してください。 [RegCreateKeyEx](http://msdn.microsoft.com/library/windows/desktop/ms724844)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `samDesired`  
 キーのセキュリティのアクセス。 既定値は KEY_READ |KEY_WRITE します。 使用可能な値と説明の一覧は、次を参照してください。 **RegCreateKeyEx**します。  
  
 *lpSecAttr*  
 ポインター、 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)構造体をキーのハンドルを子プロセスが継承できるかどうかを示します。 既定では、このパラメーターが NULL (つまり、ハンドルは継承できませんです)。  
  
 *lpdwDisposition*  
 [out]NULL 以外の場合は、REG_CREATED_NEW_KEY (キーが存在せず作成された場合)、またはポインターを取得し、(キーが存在し、開かれた) 場合。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、error_success を返しますを返し、キーを開きます。 失敗した場合は、WINERROR.H で定義されている&0; 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 **作成**設定、 [m_hKey](#m_hkey)このキーのハンドルへのメンバーです。  
  
##  <a name="a-namecregkeya--cregkeycregkey"></a><a name="cregkey"></a>CRegKey::CRegKey  
 コンストラクターです。  
  
```
CRegKey() throw();
CRegKey(CRegKey& key) throw();
explicit CRegKey(HKEY hKey) throw();
CRegKey(CAtlTransactionManager* pTM) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 `CRegKey` オブジェクトへの参照。  
  
 `hKey`  
 レジストリ キーへのハンドル。  
  
 `pTM`  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 新しい `CRegKey` オブジェクトを作成します。 既存のオブジェクトを作成することができます`CRegKey`オブジェクト、またはレジストリ キーを識別するハンドル。  
  
##  <a name="a-namedtora--cregkeycregkey"></a><a name="dtor"></a>CRegKey:: ~ CRegKey  
 デストラクターです。  
  
```
~CRegKey() throw();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターのリリース`m_hKey`します。  
  
##  <a name="a-namedeletesubkeya--cregkeydeletesubkey"></a><a name="deletesubkey"></a>CRegKey::DeleteSubKey  
 指定したキーをレジストリから削除するには、このメソッドを呼び出します。  
  
```
LONG DeleteSubKey(LPCTSTR lpszSubKey) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszSubKey`  
 削除するキーの名前を指定します。 この名前のサブキーである必要があります[m_hKey](#m_hkey)します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている&0; 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 `DeleteSubKey`サブキーがキーのみ削除できません。 キーにサブキーがある場合は、呼び出す[ある](#recursedeletekey)代わりにします。  
  
##  <a name="a-namedeletevaluea--cregkeydeletevalue"></a><a name="deletevalue"></a>CRegKey::DeleteValue  
 値フィールドを削除するには、このメソッドを呼び出す[m_hKey](#m_hkey)します。  
  
```
LONG DeleteValue(LPCTSTR lpszValue) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszValue`  
 削除する値のフィールドを指定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている&0; 以外のエラー コードが返されます。  
  
##  <a name="a-namedetacha--cregkeydetach"></a><a name="detach"></a>CRegKey::Detach  
 デタッチするには、このメソッドを呼び出して、 [m_hKey](#m_hkey)からのメンバーのハンドル、`CRegKey`オブジェクトし、設定`m_hKey`を NULL にします。  
  
```
HKEY Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 関連付けられている HKEY、`CRegKey`オブジェクトです。  
  
##  <a name="a-nameenumkeya--cregkeyenumkey"></a><a name="enumkey"></a>して  
 開いているレジストリ キーのサブキーを列挙するには、このメソッドを呼び出します。  
  
```
LONG EnumKey(  
    DWORD iIndex,
    LPTSTR pszName,
    LPDWORD pnNameLength,
    FILETIME* pftLastWriteTime = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `iIndex`  
 サブキーのインデックス。 このパラメーターは最初の呼び出しで&0; にする必要があります、次の後続の呼び出しだけインクリメントされます。  
  
 `pszName`  
 終端の null 文字も含めて、サブキーの名前を受け取るバッファーへのポインター。 サブキーの名前のみが、完全なキーの階層ではない、バッファーにコピーされます。  
  
 *戻る*  
 指定したバッファーの Tchar 単位のサイズを指定する変数へのポインター、`pszName`パラメーター。 このサイズは、終端の null 文字を含める必要があります。 メソッドが返す場合は、変数が指す*戻る*バッファーに格納されている文字の数が含まれています。 返されるカウントでは、終端の null 文字は含まれません。  
  
 *pftLastWriteTime*  
 日時を受け取る変数を指すポインター列挙されたサブキーに最後に書き込んだします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている&0; 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 サブキーを列挙するには、呼び出す`CRegKey::EnumKey`をゼロから始まるインデックス。 インデックス値をインクリメントし、メソッドが戻る ERROR_NO_MORE_ITEMS までを繰り返します。 詳細については、次を参照してください。 [RegEnumKeyEx](http://msdn.microsoft.com/library/windows/desktop/ms724862)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameflusha--cregkeyflush"></a><a name="flush"></a>CRegKey::Flush  
 すべての開いているレジストリ キーの属性をレジストリに書き込むには、このメソッドを呼び出します。  
  
```
LONG Flush() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている&0; 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [RegEnumFlush](http://msdn.microsoft.com/library/windows/desktop/ms724867)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetkeysecuritya--cregkeygetkeysecurity"></a><a name="getkeysecurity"></a>CRegKey::GetKeySecurity  
 開いているレジストリ キーを保護するセキュリティ記述子のコピーを取得するには、このメソッドを呼び出します。  
  
```
LONG GetKeySecurity(  
    SECURITY_INFORMATION si,
    PSECURITY_DESCRIPTOR psd,
    LPDWORD pnBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `si`  
 [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573)を必要なセキュリティ情報を示す値。  
  
 `psd`  
 要求されたセキュリティ記述子のコピーを受け取るバッファーへのポインター。  
  
 `pnBytes`  
 指すバッファーのバイト単位のサイズ`psd`します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 メソッドが失敗した場合、戻り値は&0; 以外のエラー コードが WINERROR で定義されているです。H.  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [RegGetKeySecurity](http://msdn.microsoft.com/library/windows/desktop/aa379313)します。  
  
##  <a name="a-namemhkeya--cregkeymhkey"></a><a name="m_hkey"></a>CRegKey::m_hKey  
 関連付けられているレジストリ キーのハンドルを含む、`CRegKey`オブジェクトです。  
  
```
HKEY m_hKey;
```  
  
##  <a name="a-namemptma--cregkeymptm"></a><a name="m_ptm"></a>CRegKey::m_pTM  
 ポインター、`CAtlTransactionManager`オブジェクトです。  
  
```
CAtlTransactionManager* m_pTM;
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namenotifychangekeyvaluea--cregkeynotifychangekeyvalue"></a><a name="notifychangekeyvalue"></a>CRegKey::NotifyChangeKeyValue  
 このメソッドでは、属性または開いているレジストリ キーの内容の変更について、呼び出し元に通知します。  
  
```
LONG NotifyChangeKeyValue(  
    BOOL bWatchSubtree,
    DWORD dwNotifyFilter,
    HANDLE hEvent,
    BOOL bAsync = TRUE) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *bWatchSubtree*  
 指定したキーとそのすべてのサブキーまたは指定したキーでのみ変更を報告するかどうかを示すフラグを指定します。 このパラメーターが TRUE の場合、キーとサブキーの変更を報告します。 パラメーターが FALSE の場合のみ、キーの変更を報告します。  
  
 *dwNotifyFilter*  
 どの変更を制御するフラグのセットを報告するかを指定します。 このパラメーターは、次の値の組み合わせを指定できます。  
  
|値|説明|  
|-----------|-------------|  
|REG_NOTIFY_CHANGE_NAME|サブキーが追加または削除された場合、呼び出し元に通知します。|  
|REG_NOTIFY_CHANGE_ATTRIBUTES|セキュリティ記述子の情報などのキーの属性への変更の呼び出し元に通知します。|  
|REG_NOTIFY_CHANGE_LAST_SET|キーの値を変更の呼び出し元に通知します。 これには、追加や、値を削除する既存の値の変更を含めることができます。|  
|REG_NOTIFY_CHANGE_SECURITY|キーのセキュリティ記述子への変更の呼び出し元に通知します。|  
  
 `hEvent`  
 イベントに対するハンドル。 場合、 *bAsync*パラメーターが TRUE の場合、メソッドからすぐに、このイベントを通知することによって変更を報告します。 場合`bAsync`false で、`hEvent`は無視されます。  
  
 `bAsync`  
 メソッドが変更を報告する方法を示すフラグを指定します。 このパラメーターが TRUE の場合、このメソッドはすぐに返され、レポートは、指定したイベントを通知することによって変更。 このパラメーターが FALSE の場合、変更が開始されるまで、メソッドは返しません。 場合`hEvent`有効なイベントが指定されていない、`bAsync`パラメーターが TRUE にすることはできません。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている&0; 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメソッドでは、指定したキーが削除された場合、呼び出し元は通知されません。  
  
 詳細およびサンプル プログラムでは、「 [RegNotifyChangeKeyValue](http://msdn.microsoft.com/library/windows/desktop/ms724892)します。  
  
##  <a name="a-nameopena--cregkeyopen"></a><a name="open"></a>Cregkey::open  
 指定したキーを開き、設定するには、このメソッドを呼び出す[m_hKey](#m_hkey)をこのキーのハンドル。  
  
```
LONG Open(  
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    REGSAM samDesired = KEY_READ | KEY_WRITE) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hKeyParent`  
 オープンするキーのハンドル。  
  
 `lpszKeyName`  
 作成したり開いたりキーの名前を指定します。 この名前のサブキーである必要があります`hKeyParent`します。  
  
 `samDesired`  
 キーのセキュリティのアクセス。 既定値は、KEY_ALL_ACCESS です。 使用可能な値と説明の一覧は、次を参照してください。 [RegCreateKeyEx](http://msdn.microsoft.com/library/windows/desktop/ms724844)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS; を返しますそれ以外の場合、0 以外のエラー値は、WINERROR で定義されます。H.  
  
### <a name="remarks"></a>コメント  
 場合、`lpszKeyName`パラメーターが NULL またはポイント空の文字列に**開いている**によって識別されるキーの新しいハンドルを開く`hKeyParent`が以前に開かれたハンドルは閉じません。  
  
 異なり[CRegKey::Create](#create)、**開く**が存在しない場合、指定したキーは作成されません。  
  
##  <a name="a-nameoperatorhkeya--cregkeyoperator-hkey"></a><a name="operator_hkey"></a>CRegKey::operator HKEY  
 変換、 `CRegKey` HKEY するオブジェクト。  
  
```  
operator HKEY() const throw();
```  
  
##  <a name="a-nameoperatoreqa--cregkeyoperator-"></a><a name="operator_eq"></a>CRegKey::operator =  
 代入演算子。  
  
```
CRegKey& operator= (CRegKey& key) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 コピーするキー。  
  
### <a name="return-value"></a>戻り値  
 新しいキーへの参照を返します。  
  
### <a name="remarks"></a>コメント  
 この演算子がデタッチ`key`その現在のオブジェクトからに割り当てます、`CRegKey`オブジェクトの代わりにします。  
  
##  <a name="a-namequerybinaryvaluea--cregkeyquerybinaryvalue"></a><a name="querybinaryvalue"></a>CRegKey::QueryBinaryValue  
 指定された値の名前のバイナリ データを取得するには、このメソッドを呼び出します。  
  
```
LONG QueryBinaryValue(  
    LPCTSTR pszValueName,
    void* pValue,
    ULONG* pnBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 クエリの値の名前を表す null で終わる文字列へのポインター。  
  
 `pValue`  
 値のデータを受け取るバッファーへのポインター。  
  
 `pnBytes`  
 バッファーのバイト単位のサイズを指定する変数へのポインターが指す、`pValue`パラメーター。 メソッドが戻るとき、この変数には、バッファーにコピーするデータのサイズが含まれています。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、error_success を返しますが返されます。 値を読み取るメソッドが失敗した場合は、WINERROR で定義されている&0; 以外のエラー コードを返します。H. 参照されているデータの種類は REG_BINARY にない場合、定義を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドでは、使用**RegQueryValueEx**し、正しい種類のデータが返されることを確認します。 参照してください[RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911)詳細です。  
  
> [!IMPORTANT]
>  このメソッドは、呼び出し元は、可能性のある信頼性の低いデータの読み取り、レジストリの場所を指定できます。 また、 [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911)このメソッドで使用する関数が明示的に NULL 終端の文字列を処理します。 呼び出し元のコードの両方の条件を確認する必要があります。  
  
##  <a name="a-namequerydwordvaluea--cregkeyquerydwordvalue"></a><a name="querydwordvalue"></a>CRegKey::QueryDWORDValue  
 指定された値の名前の DWORD データを取得するには、このメソッドを呼び出します。  
  
```
LONG QueryDWORDValue(  
    LPCTSTR pszValueName,
    DWORD& dwValue) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 クエリの値の名前を表す null で終わる文字列へのポインター。  
  
 `dwValue`  
 DWORD を受け取るバッファーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、error_success を返しますが返されます。 値を読み取るメソッドが失敗した場合は、WINERROR で定義されている&0; 以外のエラー コードを返します。H. 参照されているデータがない型 REG_DWORD の場合は、定義が返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドでは、使用**RegQueryValueEx**し、正しい種類のデータが返されることを確認します。 参照してください[RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911)詳細です。  
  
> [!IMPORTANT]
>  このメソッドは、呼び出し元は、可能性のある信頼性の低いデータの読み取り、レジストリの場所を指定できます。 また、 [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911)このメソッドで使用する関数が明示的に NULL 終端の文字列を処理します。 呼び出し元のコードの両方の条件を確認する必要があります。  
  
##  <a name="a-namequeryguidvaluea--cregkeyqueryguidvalue"></a><a name="queryguidvalue"></a>CRegKey::QueryGUIDValue  
 指定された値名の GUID のデータを取得するには、このメソッドを呼び出します。  
  
```
LONG QueryGUIDValue(  
    LPCTSTR pszValueName,
    GUID& guidValue) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 クエリの値の名前を表す null で終わる文字列へのポインター。  
  
 `guidValue`  
 GUID を受け取る変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、error_success を返しますが返されます。 値を読み取るメソッドが失敗した場合は、WINERROR で定義されている&0; 以外のエラー コードを返します。H. 参照されるデータは有効な GUID ではない場合は、定義が返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドでは、使用`CRegKey::QueryStringValue`GUID を使用して、文字列に変換し、 [CLSIDFromString](http://msdn.microsoft.com/library/windows/desktop/ms680589)します。  
  
> [!IMPORTANT]
>  このメソッドは、呼び出し元は、可能性のある信頼性の低いデータの読み取り、レジストリの場所を指定できます。  
  
##  <a name="a-namequerymultistringvaluea--cregkeyquerymultistringvalue"></a><a name="querymultistringvalue"></a>CRegKey::QueryMultiStringValue  
 指定された値名の複数文字列のデータを取得するには、このメソッドを呼び出します。  
  
```
LONG QueryMultiStringValue(  
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 クエリの値の名前を表す null で終わる文字列へのポインター。  
  
 `pszValue`  
 複数文字列のデータを受信するバッファーへのポインター。 複数文字列は、2 つの null 文字で終端の null で終わる文字列の配列です。  
  
 `pnChars`  
 サイズが指すバッファーの Tchar`pszValue`します。 メソッドが戻るとき`pnChars`終端の null 文字も含めて取得するには、複数の Tchar 単位のサイズが含まれています。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、error_success を返しますが返されます。 値を読み取るメソッドが失敗した場合は、WINERROR で定義されている&0; 以外のエラー コードを返します。H. 参照されているデータがない型 REG_MULTI_SZ の定義が返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドでは、使用**RegQueryValueEx**し、正しい種類のデータが返されることを確認します。 参照してください[RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911)詳細です。  
  
> [!IMPORTANT]
>  このメソッドは、呼び出し元は、可能性のある信頼性の低いデータの読み取り、レジストリの場所を指定できます。 また、 [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911)このメソッドで使用する関数が明示的に NULL 終端の文字列を処理します。 呼び出し元のコードの両方の条件を確認する必要があります。  
  
##  <a name="a-namequeryqwordvaluea--cregkeyqueryqwordvalue"></a><a name="queryqwordvalue"></a>CRegKey::QueryQWORDValue  
 指定された値名の QWORD データを取得するには、このメソッドを呼び出します。  
  
```
LONG QueryQWORDValue(  
    LPCTSTR pszValueName,
    ULONGLONG& qwValue) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 クエリの値の名前を表す null で終わる文字列へのポインター。  
  
 `qwValue`  
 QWORD を受け取るバッファーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、error_success を返しますが返されます。 値を読み取るメソッドが失敗した場合は、WINERROR で定義されている&0; 以外のエラー コードを返します。H. 参照されているデータの種類で定義ではありません、定義が返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドでは、使用**RegQueryValueEx**し、正しい種類のデータが返されることを確認します。 参照してください[RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911)詳細です。  
  
> [!IMPORTANT]
>  このメソッドは、呼び出し元は、可能性のある信頼性の低いデータの読み取り、レジストリの場所を指定できます。 また、 [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911)このメソッドで使用する関数が明示的に NULL 終端の文字列を処理します。 呼び出し元のコードの両方の条件を確認する必要があります。  
  
##  <a name="a-namequerystringvaluea--cregkeyquerystringvalue"></a><a name="querystringvalue"></a>CRegKey::QueryStringValue  
 指定された値名の文字列データを取得するには、このメソッドを呼び出します。  
  
```
LONG QueryStringValue(  
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 クエリの値の名前を表す null で終わる文字列へのポインター。  
  
 `pszValue`  
 文字列データを受信するバッファーへのポインター。  
  
 `pnChars`  
 サイズが指すバッファーの Tchar`pszValue`します。 メソッドが戻るとき`pnChars`を取得し、終端の null 文字を含む文字列の Tchar 単位のサイズが含まれています。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、error_success を返しますが返されます。 値を読み取るメソッドが失敗した場合は、WINERROR で定義されている&0; 以外のエラー コードを返します。H. 参照されているデータの種類 REG_SZ ではありません、定義が返されます。 メソッドが返す返します場合、`pnChars`が&0; で、必要なバッファー サイズではなく (バイト単位)。  
  
### <a name="remarks"></a>コメント  
 このメソッドでは、使用**RegQueryValueEx**し、正しい種類のデータが返されることを確認します。 参照してください[RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911)詳細です。  
  
> [!IMPORTANT]
>  このメソッドは、呼び出し元は、可能性のある信頼性の低いデータの読み取り、レジストリの場所を指定できます。 また、 [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911)このメソッドで使用する関数が明示的に NULL 終端の文字列を処理します。 呼び出し元のコードの両方の条件を確認する必要があります。  
  
##  <a name="a-namequeryvaluea--cregkeyqueryvalue"></a><a name="queryvalue"></a>CRegKey::QueryValue  
 指定した値フィールドのデータを取得するには、このメソッドを呼び出す[m_hKey](#m_hkey)します。 このメソッドの以前のバージョンが現在サポートされていませんしとマークされて**されず**します。  
  
```
LONG QueryValue(  
    LPCTSTR pszValueName,
    DWORD* pdwType,
    void* pData,
    ULONG* pnBytes) throw();

ATL_DEPRECATED LONG QueryValue(
    DWORD& dwValue,
    LPCTSTR lpszValueName);

ATL_DEPRECATED LONG QueryValue(
    LPTSTR szValue,
    LPCTSTR lpszValueName,
    DWORD* pdwCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 クエリの値の名前を表す null で終わる文字列へのポインター。 場合`pszValueName`が NULL または空の文字列""メソッドが型を取得、およびキーのデータが名前のないか、存在する場合、既定値です。  
  
 `pdwType`  
 指定した値に格納されたデータの種類を示すコードを受け取る変数へのポインター。 `pdwType`型コードが必要ない場合、パラメーターは NULL を指定できます。  
  
 `pData`  
 値のデータを受け取るバッファーへのポインター。 このパラメーターは、データが必要ない場合、NULL にすることができます。  
  
 `pnBytes`  
 バッファーのバイト単位のサイズを指定する変数へのポインターが指す、`pData`パラメーター。 この変数には、メソッドが戻るときにコピーするデータのサイズが含まれています*pData します。*  
  
 `dwValue`  
 値フィールドの数値データ。  
  
 `lpszValueName`  
 クエリを実行する、値フィールドを指定します。  
  
 `szValue`  
 値フィールドの文字列データです。  
  
 `pdwCount`  
 文字列データのサイズ。 サイズには、その値は設定された最初に、`szValue`バッファー。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS; を返しますそれ以外の場合、0 以外のエラー コードは、WINERROR で定義されます。H.  
  
### <a name="remarks"></a>コメント  
 2 つの元バージョン`QueryValue`はサポートされなくなり、としてマークされて**されず**します。 これらの形式が使用されている場合、コンパイラは警告を発行します。  
  
 残りのメソッドは、RegQueryValueEx を呼び出します。  
  
> [!IMPORTANT]
>  このメソッドは、呼び出し元は、可能性のある信頼性の低いデータの読み取り、レジストリの場所を指定できます。 また、このメソッドで使用する RegQueryValueEx 関数は明示的に文字列は処理しませんは`NULL`は終了します。 呼び出し元のコードの両方の条件を確認する必要があります。  
  
##  <a name="a-namerecursedeletekeya--cregkeyrecursedeletekey"></a><a name="recursedeletekey"></a>CRegKey::RecurseDeleteKey  
 指定したキーをレジストリから削除し、すべてのサブキーを明示的に削除するには、このメソッドを呼び出します。  
  
```
LONG RecurseDeleteKey(LPCTSTR lpszKey) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszKey*  
 削除するキーの名前を指定します。 この名前のサブキーである必要があります[m_hKey](#m_hkey)します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS; を返しますそれ以外の場合、0 以外のエラー値は、WINERROR で定義されます。H.  
  
### <a name="remarks"></a>コメント  
 キーにサブキーがある場合は、キーを削除するには、このメソッドを呼び出す必要があります。  
  
##  <a name="a-namesetbinaryvaluea--cregkeysetbinaryvalue"></a><a name="setbinaryvalue"></a>CRegKey::SetBinaryValue  
 レジストリ キーのバイナリ値を設定するには、このメソッドを呼び出します。  
  
```
LONG SetBinaryValue(  
    LPCTSTR pszValueName,
    const void* pValue,
    ULONG nBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 設定する値の名前を格納する文字列へのポインター。 この名前の値がまだ存在しない場合は、メソッドによりキーに追加されます。  
  
 `pValue`  
 指定された値の名前で保存するデータを格納するバッファーへのポインター。  
  
 `nBytes`  
 指す情報のバイト単位のサイズを指定、`pValue`パラメーター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている&0; 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して[RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923)に値をレジストリに書き込めません。  
  
##  <a name="a-namesetdwordvaluea--cregkeysetdwordvalue"></a><a name="setdwordvalue"></a>CRegKey::SetDWORDValue  
 レジストリ キーの DWORD 値を設定するには、このメソッドを呼び出します。  
  
```
LONG SetDWORDValue(LPCTSTR pszValueName, DWORD dwValue) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 設定する値の名前を格納する文字列へのポインター。 この名前の値がまだ存在しない場合は、メソッドによりキーに追加されます。  
  
 `dwValue`  
 指定された値の名前で保存する DWORD データ。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている&0; 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して[RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923)に値をレジストリに書き込めません。  
  
##  <a name="a-namesetguidvaluea--cregkeysetguidvalue"></a><a name="setguidvalue"></a>CRegKey::SetGUIDValue  
 レジストリ キーの GUID 値を設定するには、このメソッドを呼び出します。  
  
```
LONG SetGUIDValue(LPCTSTR pszValueName, REFGUID guidValue) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 設定する値の名前を格納する文字列へのポインター。 この名前の値がまだ存在しない場合は、メソッドによりキーに追加されます。  
  
 `guidValue`  
 指定された値の名前で保存する GUID への参照。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている&0; 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドでは、使用`CRegKey::SetStringValue`GUID を使用して文字列に変換し、 [StringFromGUID2](http://msdn.microsoft.com/library/windows/desktop/ms683893)します。  
  
##  <a name="a-namesetkeyvaluea--cregkeysetkeyvalue"></a><a name="setkeyvalue"></a>CRegKey::SetKeyValue  
 指定したキーの指定した値フィールドにデータを格納するには、このメソッドを呼び出します。  
  
```
LONG SetKeyValue(  
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszKeyName`  
 作成したり開いたりキーの名前を指定します。 この名前のサブキーである必要があります[m_hKey](#m_hkey)します。  
  
 `lpszValue`  
 格納されるデータを指定します。 このパラメーターは、NULL を指定する必要があります。  
  
 `lpszValueName`  
 設定する値 フィールドを指定します。 キーにもこの名前の値フィールドが既に存在しない場合は、追加されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS; を返しますそれ以外の場合、0 以外のエラー コードは、WINERROR で定義されます。H.  
  
### <a name="remarks"></a>コメント  
 このメソッドを作成したり開いたり、`lpszKeyName`キーを格納、`lpszValue`内のデータ、`lpszValueName`値フィールドです。  
  
##  <a name="a-namesetkeysecuritya--cregkeysetkeysecurity"></a><a name="setkeysecurity"></a>CRegKey::SetKeySecurity  
 レジストリ キーのセキュリティを設定するには、このメソッドを呼び出します。  
  
```
LONG SetKeySecurity(SECURITY_INFORMATION si, PSECURITY_DESCRIPTOR psd) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `si`  
 設定するセキュリティ記述子のコンポーネントを指定します。 値は、次の値の組み合わせにすることができます。  
  
|値|説明|  
|-----------|-------------|  
|DACL_SECURITY_INFORMATION|キーの随意アクセス制御リスト (DACL) を設定します。 呼び出し元プロセスは、オブジェクトの所有者である必要がありますか、キーは WRITE_DAC アクセスにあります。|  
|GROUP_SECURITY_INFORMATION|キーのプライマリ グループ セキュリティ識別子 (SID) を設定します。 呼び出し元プロセスは、オブジェクトの所有者である必要がありますか、キーは WRITE_OWNER アクセスにあります。|  
|OWNER_SECURITY_INFORMATION|キーの所有者の SID を設定します。 呼び出し元のプロセスは、オブジェクトの所有者であるか有効になっている SE_TAKE_OWNERSHIP_NAME 権限を持っている必要がありますか、キーが WRITE_OWNER アクセスにあります。|  
|SACL_SECURITY_INFORMATION|キーのシステム アクセス制御リスト (SACL) を設定します。 ACCESS_SYSTEM_SECURITY アクセス キーが必要です。 このアクセス権を取得するための適切が SE_SECURITY_NAME を有効にするには[特権](http://msdn.microsoft.com/library/windows/desktop/aa379306)呼び出し元の現在のアクセス トークンで ACCESS_SYSTEM_SECURITY アクセスのためのハンドルを開くし、特権を無効にします。|  
  
 `psd`  
 ポインター、 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)を指定したキーに設定するセキュリティ属性を指定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている&0; 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 キーのセキュリティ属性を設定します。 参照してください[RegSetKeySecurity](http://msdn.microsoft.com/library/windows/desktop/aa379314)詳細です。  
  
##  <a name="a-namesetmultistringvaluea--cregkeysetmultistringvalue"></a><a name="setmultistringvalue"></a>CRegKey::SetMultiStringValue  
 レジストリ キーの複数文字列の値を設定するには、このメソッドを呼び出します。  
  
```
LONG SetMultiStringValue(LPCTSTR pszValueName, LPCTSTR pszValue) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 設定する値の名前を格納する文字列へのポインター。 この名前の値がまだ存在しない場合は、メソッドによりキーに追加されます。  
  
 `pszValue`  
 指定された値の名前で保存する複数文字列のデータへのポインター。 複数文字列は、2 つの null 文字で終端の null で終わる文字列の配列です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている&0; 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して[RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923)に値をレジストリに書き込めません。  
  
##  <a name="a-namesetqwordvaluea--cregkeysetqwordvalue"></a><a name="setqwordvalue"></a>CRegKey::SetQWORDValue  
 レジストリ キーの QWORD 値を設定するには、このメソッドを呼び出します。  
  
```
LONG SetQWORDValue(LPCTSTR pszValueName, ULONGLONG qwValue) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 設定する値の名前を格納する文字列へのポインター。 この名前の値がまだ存在しない場合は、メソッドによりキーに追加されます。  
  
 `qwValue`  
 指定された値の名前で保存する QWORD データ。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている&0; 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して[RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923)に値をレジストリに書き込めません。  
  
##  <a name="a-namesetstringvaluea--cregkeysetstringvalue"></a><a name="setstringvalue"></a>CRegKey::SetStringValue  
 レジストリ キーの文字列値を設定します。  
  
```
LONG SetStringValue(  
    LPCTSTR pszValueName,
    LPCTSTR pszValue,
    DWORD dwType = REG_SZ) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 設定する値の名前を格納する文字列へのポインター。 この名前の値がまだ存在しない場合は、メソッドによりキーに追加されます。  
  
 `pszValue`  
 指定された値名で格納される文字列データへのポインター。  
  
 `dwType`  
 レジストリに書き込む文字列の型。REG_SZ (既定値) または REG_EXPAND_SZ (複数文字列の場合)。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS を返します。 失敗した場合は、WINERROR.H で定義されている&0; 以外のエラー コードが返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して[RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923\(v=vs.85\).aspx)に値をレジストリに書き込めません。  
  
##  <a name="a-namesetvaluea--cregkeysetvalue"></a><a name="setvalue"></a>CRegKey::SetValue  
 指定した値フィールドにデータを格納するには、このメソッドを呼び出す[m_hKey](#m_hkey)します。 このメソッドの以前のバージョンが現在サポートされていませんしとマークされて**されず**します。  
  
```
LONG SetValue(  
    LPCTSTR pszValueName,
    DWORD dwType,
    const void* pValue,
    ULONG nBytes) throw();
    
static LONG WINAPI SetValue(  
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL);

ATL_DEPRECATED LONG SetValue(  
    DWORD dwValue,
    LPCTSTR lpszValueName);

ATL_DEPRECATED LONG SetValue(  
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL,
    bool bMulti = false,
    int nValueLen = -1);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszValueName`  
 設定する値の名前を格納する文字列へのポインター。 この名前の値がキーに存在しない、メソッドによりキーに追加されます。 場合`pszValueName`が NULL または空の文字列""の種類を設定する方法、およびキーのデータが名前のない値または既定値です。  
  
 `dwType`  
 参照するデータの種類を示すコードを指定します、`pValue`パラメーター。  
  
 `pValue`  
 指定された値の名前で保存するデータを格納するバッファーへのポインター。  
  
 `nBytes`  
 指す情報のバイト単位のサイズを指定、`pValue`パラメーター。 データの場合は型が REG_SZ、REG_EXPAND_SZ、または、REG_MULTI_SZ`nBytes`終端の null 文字のサイズを含める必要があります。  
  
 `hKeyParent`  
 オープンするキーのハンドル。  
  
 `lpszKeyName`  
 作成したり開いたりキーの名前を指定します。 この名前のサブキーである必要があります`hKeyParent`します。  
  
 `lpszValue`  
 格納されるデータを指定します。 このパラメーターは、NULL を指定する必要があります。  
  
 `lpszValueName`  
 設定する値 フィールドを指定します。 キーにもこの名前の値フィールドが既に存在しない場合は、追加されます。  
  
 `dwValue`  
 格納されるデータを指定します。  
  
 `bMulti`  
 False の場合は、文字列は次の種類が REG_SZ を示します。 True の場合は、文字列は、REG_MULTI_SZ の型の複数文字列を示します。  
  
 `nValueLen`  
 場合`bMulti`が true の場合`nValueLen`の長さ、 *lpszValue*文字列の文字。 場合`bMulti`が false の場合、メソッドの計算で、長さが自動的に処理が-1 の値を示します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、ERROR_SUCCESS; を返しますそれ以外の場合、0 以外のエラー コードは、WINERROR で定義されます。H.  
  
### <a name="remarks"></a>コメント  
 2 つの元バージョン`SetValue`としてマークされて**されず**使用する必要があります。 これらの形式が使用されている場合、コンパイラは警告を発行します。  
  
 3 番目のメソッド呼び出し[RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923)します。  
  
## <a name="see-also"></a>関連項目  
 [DCOM のサンプル](../../visual-cpp-samples.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

