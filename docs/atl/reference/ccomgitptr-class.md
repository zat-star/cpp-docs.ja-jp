---
title: "CComGITPtr クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComGITPtr
- ATLBASE/ATL::CComGITPtr
- ATLBASE/ATL::CComGITPtr::CComGITPtr
- ATLBASE/ATL::CComGITPtr::Attach
- ATLBASE/ATL::CComGITPtr::CopyTo
- ATLBASE/ATL::CComGITPtr::Detach
- ATLBASE/ATL::CComGITPtr::GetCookie
- ATLBASE/ATL::CComGITPtr::Revoke
- ATLBASE/ATL::CComGITPtr::m_dwCookie
dev_langs:
- C++
helpviewer_keywords:
- CComGITPtr class
ms.assetid: af895acb-525a-4555-bb67-b241b7df515b
caps.latest.revision: 19
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
ms.openlocfilehash: 9fe9d9f6d03a6d72c1ce3332419c738570a53803
ms.lasthandoff: 02/24/2017

---
# <a name="ccomgitptr-class"></a>CComGITPtr クラス
このクラスは、インターフェイス ポインターを処理するためのメソッドとグローバル インターフェイス テーブル (GIT) を提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class CComGITPtr
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 GIT に格納されるインターフェイス ポインターの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComGITPtr::CComGITPtr](#ccomgitptr)|コンストラクターです。|  
|[CComGITPtr:: ~ CComGITPtr](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComGITPtr::Attach](#attach)|グローバル インターフェイス テーブル (GIT) でインターフェイス ポインターを登録するには、このメソッドを呼び出します。|  
|[CComGITPtr::CopyTo](#copyto)|インターフェイスをグローバル インターフェイス テーブル (GIT) から渡されたポインターにコピーするには、このメソッドを呼び出します。|  
|[CComGITPtr::Detach](#detach)|インターフェイスの関連付けを解除するには、このメソッドを呼び出して、`CComGITPtr`オブジェクトです。|  
|[CComGITPtr::GetCookie](#getcookie)|Cookie を返すには、このメソッドを呼び出す、`CComGITPtr`オブジェクトです。|  
|[CComGITPtr::Revoke](#revoke)|グローバル インターフェイス テーブル (GIT) から、インターフェイスを削除するには、このメソッドを呼び出します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CComGITPtr::operator DWORD](#operator_dword)|Cookie を返す、`CComGITPtr`オブジェクトです。|  
|[CComGITPtr::operator =](#operator_eq)|代入演算子。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComGITPtr::m_dwCookie](#m_dwcookie)|クッキー。|  
  
## <a name="remarks"></a>コメント  
 フリー スレッド マーシャラーを集約し、他のオブジェクトから取得したインターフェイス ポインターを使用する必要があるオブジェクトには、インターフェイスが正しくマーシャ リングすることを確認する特別な手順を実行する必要があります。 通常これは、GIT でインターフェイス ポインターを格納して、GIT を使用するたびからポインターを取得します。 クラス`CComGITPtr`GIT に格納されているインターフェイス ポインターを使用するために提供されます。  
  
> [!NOTE]
>  グローバル インターフェイス テーブルの機能は Windows 95 DCOM バージョン 1.1 をし、その後、Windows 98、Windows NT 4.0 Service Pack 3 以降および Windows 2000 にできるだけです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="attach"></a>CComGITPtr::Attach  
 グローバル インターフェイス テーブル (GIT) でインターフェイス ポインターを登録するには、このメソッドを呼び出します。  
  
```
HRESULT Attach(T* p) throw();

HRESULT Attach(DWORD dwCookie) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 GIT に追加するインターフェイス ポインター。  
  
 `dwCookie`  
 インターフェイス ポインターを識別するために使用されるクッキー。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドでは、GIT が有効でない場合、またはクッキーが NULL の場合に、アサーション エラーが発生します。  
  
##  <a name="ccomgitptr"></a>CComGITPtr::CComGITPtr  
 コンストラクターです。  
  
```
CComGITPtr() throw();
CComGITPtr(T* p);
CComGITPtr(const CComGITPtr& git);
explicit CComGITPtr(DWORD dwCookie) throw();
CComGITPtr(CComGITPtr&& rv);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `p`  
 グローバル インターフェイス テーブル (GIT) に格納されるインターフェイス ポインター。  
  
 [入力] `git`  
 既存への参照を`CComGITPtr`オブジェクトです。  
  
 [入力] `dwCookie`  
 インターフェイス ポインターを識別するために使用されるクッキー。  
  
 [入力] `rv`  
 ソース`CComGITPtr`からデータを移動するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 新しい`CComGITPtr`オブジェクトを必要に応じて、既存`CComGITPtr`オブジェクトです。  
  
 コンス トラクターを使用して`rv`移動コンス トラクターです。 元のデータを移動`rv`、し`rv`がオフになっています。  
  
##  <a name="dtor"></a>CComGITPtr:: ~ CComGITPtr  
 デストラクターです。  
  
```
~CComGITPtr() throw();
```  
  
### <a name="remarks"></a>コメント  
 グローバル インターフェイス テーブル (GIT) からのインターフェイスの削除を使用して[CComGITPtr::Revoke](#revoke)します。  
  
##  <a name="copyto"></a>CComGITPtr::CopyTo  
 インターフェイスをグローバル インターフェイス テーブル (GIT) から渡されたポインターにコピーするには、このメソッドを呼び出します。  
  
```
HRESULT CopyTo(T** pp) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pp`  
 インターフェイスを受信するためのポインターです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 GIT からのインターフェイスは、渡されたポインターにコピーされます。 必要でなくなったとき、呼び出し元が、ポインターを解放する必要があります。  
  
##  <a name="detach"></a>CComGITPtr::Detach  
 インターフェイスの関連付けを解除するには、このメソッドを呼び出して、`CComGITPtr`オブジェクトです。  
  
```
DWORD Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 Cookie を返す、`CComGITPtr`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 呼び出し元、GIT からのインターフェイスを削除する責任はユーザーが使用して[CComGITPtr::Revoke](#revoke)します。  
  
##  <a name="getcookie"></a>CComGITPtr::GetCookie  
 Cookie を返すには、このメソッドを呼び出す、`CComGITPtr`オブジェクトです。  
  
```
DWORD GetCookie() const;
```  
  
### <a name="return-value"></a>戻り値  
 Cookie を返します。  
  
### <a name="remarks"></a>コメント  
 Cookie は、インターフェイスとその場所を識別するために使用される変数です。  
  
##  <a name="m_dwcookie"></a>CComGITPtr::m_dwCookie  
 クッキー。  
  
```
DWORD m_dwCookie;
```  
  
### <a name="remarks"></a>コメント  
 Cookie は、インターフェイスとその場所を識別するために使用するメンバー変数です。  
  
##  <a name="operator_eq"></a>CComGITPtr::operator =  
 代入演算子です。  
  
```
CComGITPtr& operator= (T* p);
CComGITPtr& operator= (const CComGITPtr& git);
CComGITPtr& operator= (DWORD dwCookie);
CComGITPtr& operator= (CComGITPtr&& rv);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `p`  
 インターフェイスへのポインター。  
  
 [入力] `git`  
 `CComGITPtr` オブジェクトへの参照。  
  
 [入力] `dwCookie`  
 インターフェイス ポインターを識別するために使用されるクッキー。  
  
 [入力] `rv`  
 `CComGITPtr`からデータを移動します。  
  
### <a name="return-value"></a>戻り値  
 取得、更新された`CComGITPtr`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 新しい値を代入、`CComGITPtr`既存のオブジェクトとは、グローバル インターフェイス テーブルへの参照からのオブジェクト。  
  
##  <a name="operator_dword"></a>CComGITPtr::operator DWORD  
 関連付けられているクッキーを返す、`CComGITPtr`オブジェクトです。  
  
```  
operator DWORD() const;
```  
  
### <a name="remarks"></a>コメント  
 Cookie は、インターフェイスとその場所を識別するために使用される変数です。  
  
##  <a name="revoke"></a>CComGITPtr::Revoke  
 グローバル インターフェイス テーブル (GIT) から現在のインターフェイスを削除するには、このメソッドを呼び出します。  
  
```
HRESULT Revoke() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 GIT からのインターフェイスを削除します。  
  
## <a name="see-also"></a>関連項目  
 [フリー スレッド マーシャラー](../../atl/atl-and-the-free-threaded-marshaler.md)   
 [アパートメント間でインターフェイスへのアクセス](http://msdn.microsoft.com/library/windows/desktop/ms682353)   
 [グローバル インターフェイス テーブルを使用する場合](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [クラスの概要](../../atl/atl-class-overview.md)

