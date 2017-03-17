---
title: "CSettingsStore クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore::CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore::Close
- AFXSETTINGSSTORE/CSettingsStore::CreateKey
- AFXSETTINGSSTORE/CSettingsStore::DeleteKey
- AFXSETTINGSSTORE/CSettingsStore::DeleteValue
- AFXSETTINGSSTORE/CSettingsStore::Open
- AFXSETTINGSSTORE/CSettingsStore::Read
- AFXSETTINGSSTORE/CSettingsStore::Write
dev_langs:
- C++
helpviewer_keywords:
- CSettingsStore class
ms.assetid: 0ea181de-a13e-4b29-b560-7c43838223ff
caps.latest.revision: 29
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
ms.sourcegitcommit: 0b07f6b12e178d8e324313ea3b0f6de9ae7420c9
ms.openlocfilehash: 0918c8dd9b6284adecb61bc95ddfd41c22d16cb8
ms.lasthandoff: 02/24/2017

---
# <a name="csettingsstore-class"></a>CSettingsStore Class
Windows API 関数をラップし、レジストリへのアクセスに使用するオブジェクト指向インターフェイスを提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CSettingsStore : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSettingsStore::CSettingsStore](#csettingsstore)|`CSettingsStore` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSettingsStore::Close](#close)|開いているレジストリ キーを閉じます。|  
|[CSettingsStore::CreateKey](#createkey)|指定したキーを開くか、存在しない場合は作成されます。|  
|[CSettingsStore::DeleteKey](#deletekey)|指定したキーとそのすべての子を削除します。|  
|[CSettingsStore::DeleteValue](#deletevalue)|開いているキーの指定した値を削除します。|  
|[CSettingsStore::Open](#open)|指定したキーを開きます。|  
|[CSettingsStore::Read](#read)|指定したキー値のデータを取得します。|  
|[CSettingsStore::Write](#write)|開いているキーの下のレジストリに値を書き込みます。|  
  
## <a name="remarks"></a>コメント  
 メンバー関数は、`CreateKey`と`Open`とよく似ています。 レジストリ キーが既に存在する場合`CreateKey`と`Open`同じように機能します。 ただし、レジストリ キーが存在しない場合、`CreateKey`一方が作成されます`Open`エラー値が返されます。  
  
## <a name="example"></a>例  
 次の例では、メソッドを開くと Read メソッドを使用して、`CSettingsStore`クラスです。 このコード スニペットの一部である、[ツール ヒントのデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_ToolTipDemo&#1;](../../mfc/reference/codesnippet/cpp/csettingsstore-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CSettingsStore`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxsettingsstore.h  
  
##  <a name="close"></a>CSettingsStore::Close  
 開いているレジストリ キーを閉じます。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>コメント  
 既定では、このメソッドは、デストラクターから、 [CSettingsStore クラス](../../mfc/reference/csettingsstore-class.md)します。  
  
##  <a name="createkey"></a>CSettingsStore::CreateKey  
 レジストリ キーを開くか、存在しない場合は作成されます。  
  
```  
virtual BOOL CreateKey(LPCTSTR pszPath);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pszPath`  
 作成したり開いたりキーの名前を指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は&0;それ以外の場合&0; 以外の値。  
  
### <a name="remarks"></a>コメント  
 `CreateKey`使用して`m_hKey`レジストリの照会のルートとして。 検索`pszPath`のサブキーとして`m_hKey`します。 キーが存在しない場合`CreateKey`によって作成されます。 それ以外の場合、キーを開きます。 `CreateKey`設定し、`m_hKey`作成または開いているキーにします。  
  
##  <a name="csettingsstore"></a>CSettingsStore::CSettingsStore  
 
          `CSettngsStore` オブジェクトを作成します。  
  
```  
CSettingsStore(
    BOOL bAdmin,  
    BOOL bReadOnly);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bAdmin`  
 指定するブール値パラメーターかどうか、`CSettingsStore`オブジェクトが管理者モードで動作しています。  
  
 [入力] `bReadOnly`  
 指定するブール値パラメーターかどうか、`CSettingsStore`オブジェクトが読み取り専用モードに作成します。  
  
### <a name="remarks"></a>コメント  
 場合`bAdmin`に設定されている`false`、`m_hKey`にメンバー変数が設定されている`HKEY_LOCAL_MACHINE`します。 If you set `bAdmin` to `true`, `m_hKey` is set to `HKEY_CURRENT_USER`.  
  
 セキュリティのアクセス権によって異なります、`bReadOnly`パラメーター。 場合`bReadonly`は`false`、セキュリティのアクセスに設定されます`KEY_ALL_ACCESS`します。 場合`bReadyOnly`は`true`、セキュリティのアクセスは、の組み合わせに設定されます`KEY_QUERY_VALUE, KEY_NOTIFY`と`KEY_ENUMERATE_SUB_KEYS`です。 レジストリとセキュリティのアクセスの詳細については、次を参照してください。[レジストリ キーのセキュリティとアクセス権](http://msdn.microsoft.com/library/windows/desktop/ms724878)します。  
  
 デストラクターを`CSettingsStore`解放`m_hKey`自動的にします。  
  
##  <a name="deletekey"></a>CSettingsStore::DeleteKey  
 レジストリからキーとそのすべての子を削除します。  
  
```  
virtual BOOL DeleteKey(
    LPCTSTR pszPath,  
    BOOL bAdmin = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pszPath`  
 削除するキーの名前。  
  
 [入力] `bAdmin`  
 削除するキーの場所を指定するスイッチです。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドが失敗、`CSettingsStore`オブジェクトが読み取り専用モードにします。  
  
 場合、パラメーター `bAdmin`&0; の場合は、`DeleteKey`の下で削除するキーの検索`HKEY_CURRENT_USER`します。 場合`bAdmin`がゼロ以外、`DeleteKey`の下で削除するキーの検索`HKEY_LOCAL_MACHINE`します。  
  
##  <a name="deletevalue"></a>CSettingsStore::DeleteValue  
 値を削除`m_hKey`します。  
  
```  
virtual BOOL DeleteValue(LPCTSTR pszValue);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pszValue`  
 削除する値のフィールドを指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="open"></a>CSettingsStore::Open  
 レジストリ キーを開きます。  
  
```  
virtual BOOL Open(LPCTSTR pszPath);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pszPath`  
 レジストリ キーの名前。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 設定されているこのメソッドは、指定したキーを正常に開いたら、`m_hKey`をこのキーのハンドル。  
  
##  <a name="read"></a>CSettingsStore::Read  
 レジストリのキーから値を読み取ります。  
  
```  
virtual BOOL Read(
    LPCTSTR pszKey,  
    int& iVal);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    DWORD& dwVal);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CString& sVal);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CStringList& scStringList);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CStringArray& scArray);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CDWordArray& dwcArray);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CWordArray& wcArray);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CByteArray& bcArray);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    LPPOINT& lpPoint);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CRect& rect);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    BYTE** ppData,  
    UINT* pBytes);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CObList& list);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CObject& obj);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CObject*& pObj);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pszKey`  
 レジストリから読み取る値の名前を表す null で終わる文字列へのポインター。  
  
 [出力] `iVal`  
 レジストリ キーから読み取った値を受け取る整数変数への参照。  
  
 [出力] `dwVal`  
 レジストリ キーから読み取る値を受け取る 32 ビットのダブルワードの変数への参照。  
  
 [出力] `sVal`  
 レジストリ キーから読み取った値を受け取る文字列変数への参照。  
  
 [出力] `scStringList`  
 レジストリ キーから読み取った値を受け取る文字列リストの変数への参照。  
  
 [出力] `scArray`  
 レジストリ キーから読み取った値を受け取る文字列配列の変数への参照。  
  
 [出力] `dwcArray`  
 レジストリ キーから読み取る値を受け取る 32 ビットのダブルワードの配列変数への参照。  
  
 [出力] `wcArray`  
 レジストリ キーから読み取った値を受け取る 16 ビット ワードの配列変数への参照。  
  
 [出力] `bcArray`  
 レジストリ キーから読み取った値を受信するバイト配列の変数への参照。  
  
 [出力] `lpPoint`  
 ポインターへの参照、`POINT`レジストリ キーの値を受け取る構造体を読み取る。  
  
 [出力] `rect`  
 参照、 [CRect](../../atl-mfc-shared/reference/crect-class.md)レジストリ キーから値を受け取る変数を読み取る。  
  
 [出力] `ppData`  
 レジストリ キーから読み取る値を受け取るデータへのポインターへのポインター。  
  
 [出力] `pBytes`  
 符号なし整数型の変数へのポインター。 この変数には、バッファーのサイズを`ppData`をポイントします。  
  
 [出力] `list`  
 参照、 [CObList](../../mfc/reference/coblist-class.md)レジストリ キーから値を受け取る変数を読み取る。  
  
 [出力] `obj`  
 参照、 [CObject](../../mfc/reference/cobject-class.md)レジストリ キーから値を受け取る変数を読み取る。  
  
 [出力] `pObj`  
 ポインターへの参照、`CObject`レジストリ キーから値を受け取る変数を読み取る。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `Read`チェック`pszKey`のサブキーとして`m_hKey`します。  
  
##  <a name="write"></a>CSettingsStore::Write  
 開いているキーの下のレジストリに値を書き込みます。  
  
```  
virtual BOOL Write(
    LPCTSTR pszKey,  
    int iVal);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    DWORD dwVal);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    LPCTSTR pszVal);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CStringList& scStringList);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CByteArray& bcArray);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CStringArray& scArray);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CDWordArray& dwcArray);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CWordArray& wcArray);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    const CRect& rect);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    LPPOINT& lpPoint);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    LPBYTE pData,  
    UINT nBytes);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CObList& list);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CObject& obj);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CObject* pObj);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pszKey`  
 設定する値の名前を含む文字列へのポインター。  
  
 [入力] `iVal`  
 格納するデータを含む整数の変数への参照。  
  
 [入力] `dwVal`  
 格納するデータを含む 32 ビットのダブルワード変数への参照。  
  
 [入力] `pszVal`  
 格納するデータを含む null で終わる文字列変数へのポインター。  
  
 [入力] `scStringList`  
 参照、 [CStringList](../../mfc/reference/cstringlist-class.md)を格納するデータを含む変数。  
  
 [入力] `bcArray`  
 格納するデータを含むバイト配列の変数への参照。  
  
 [入力] `scArray`  
 格納するデータを含む文字列配列の変数への参照。  
  
 [入力] `dwcArray`  
 32 ビットのダブルワードの配列変数を格納するデータを含むへの参照。  
  
 [入力] `wcArray`  
 16 ビット ワードの配列変数を格納するデータを含むへの参照。  
  
 [入力] `rect`  
 参照、 [CRect](../../atl-mfc-shared/reference/crect-class.md)を格納するデータを含む変数。  
  
 [入力] `lpPoint`  
 ポインターへの参照、`POINT`を格納するデータを含む変数。  
  
 [入力] `pData`  
 格納するデータを格納するバッファーへのポインター。  
  
 [入力] `nBytes`  
 サイズを指定しているデータのバイト数、`pData`パラメーター ポイントです。  
  
 [入力] `list`  
 参照、 [CObList](../../mfc/reference/coblist-class.md)を格納するデータを含む変数。  
  
 [入力] `obj`  
 参照、 [CObject](../../mfc/reference/cobject-class.md)を格納するデータを含む変数。  
  
 [入力] `pObj`  
 ポインターへのポインター、`CObject`を格納するデータを含む変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は `TRUE`。それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
 レジストリへの書き込みをするように設定する必要があります`bReadOnly`0 以外の値を作成するときに、 [CSettingsStore](../../mfc/reference/csettingsstore-class.md)オブジェクトです。 詳細については、次を参照してください。 [CSettingsStore::CSettingsStore](#csettingsstore)します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)

