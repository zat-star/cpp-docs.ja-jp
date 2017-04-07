---
title: "CComUnkArray クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComUnkArray
- ATLCOM/ATL::CComUnkArray
- ATLCOM/ATL::CComUnkArray::CComUnkArray
- ATLCOM/ATL::CComUnkArray::Add
- ATLCOM/ATL::CComUnkArray::begin
- ATLCOM/ATL::CComUnkArray::end
- ATLCOM/ATL::CComUnkArray::GetCookie
- ATLCOM/ATL::CComUnkArray::GetUnknown
- ATLCOM/ATL::CComUnkArray::Remove
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- CComUnkArray class
ms.assetid: 5fd4b378-a7b5-4cc1-8866-8ab72a73639e
caps.latest.revision: 17
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 94f1062ff3808f527874a8890eca95c9b655b1bf
ms.lasthandoff: 02/24/2017

---
# <a name="ccomunkarray-class"></a>CComUnkArray クラス
このクラスは、格納**IUnknown**ポインターへのパラメーターとして使用するものでは、 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)テンプレート クラス。  
  
## <a name="syntax"></a>構文  
  
```
template<unsigned int nMaxSize>
class CComUnkArray
```  
  
#### <a name="parameters"></a>パラメーター  
 *nMaxSize*  
 最大数**IUnknown**静的な配列に格納できるポインターです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComUnkArray::CComUnkArray](#ccomunkarray)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComUnkArray::Add](#add)|追加するには、このメソッドを呼び出して、 **IUnknown**配列へのポインター。|  
|[CComUnkArray::begin](#begin)|最初のポインターを返します**IUnknown**コレクション内のポインター。|  
|[CComUnkArray::end](#end)|最後に、ポインターを返します**IUnknown**コレクション内のポインター。|  
|[CComUnkArray::GetCookie](#getcookie)|関連付けられているクッキーを取得するには、このメソッドを呼び出して、指定された**IUnknown**ポインター。|  
|[CComUnkArray::GetUnknown](#getunknown)|このメソッドを呼び出して取得、 **IUnknown**与えられたクッキーに関連付けられたポインター。|  
|[CComUnkArray::Remove](#remove)|削除するには、このメソッドを呼び出す、 **IUnknown**ポインター、配列に格納します。|  
  
## <a name="remarks"></a>コメント  
 **CComUnkArray**に含まれる固定数**IUnknown**ポインター、接続のインターフェイスが各をポイントします。 **CComUnkArray**をパラメーターとして使用できる、 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)テンプレート クラス。 **CComUnkArray\<1 >**テンプレート特殊化**CComUnkArray**の&1; つの接続ポイントが最適化されています。  
  
 **CComUnkArray**メソッド[開始](#begin)と[エンド](#end)(たとえば、イベントが発生したときに) すべてのコネクション ポイントをループするために使用できます。  
  
 参照してください[オブジェクトのコネクション ポイントの追加](../../atl/adding-connection-points-to-an-object.md)接続の作成を自動化することの詳細については、プロキシをポイントします。  
  
> [!NOTE]
> **注**クラス[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)によって使用される、**クラスの追加**コネクション ポイントを持つコントロールを作成するときにウィザード。 コネクション ポイントの数を手動で指定する場合は、変更からの参照**CComDynamicUnkArray**に`CComUnkArray<` *n* `>`ここで、 *n*のために必要な接続ポイントの数です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="add"></a>CComUnkArray::Add  
 追加するには、このメソッドを呼び出して、 **IUnknown**配列へのポインター。  
  
```
DWORD Add(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 追加するには、このメソッドを呼び出して、 **IUnknown**配列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 配列は、新しいポインターを格納するのに十分な大きさがない場合は、新しく追加されたポインター、または 0 に関連付けられているクッキーを返します。  
  
##  <a name="begin"></a>CComUnkArray::begin  
 コレクションの先頭にポインターを返す**IUnknown**インターフェイス ポインター。  
  
```
IUnknown**
    begin();
```     
  
### <a name="return-value"></a>戻り値  
 ポインター、 **IUnknown**インターフェイス ポインター。  
  
### <a name="remarks"></a>コメント  
 コレクションには、としてローカルに格納されているインターフェイスへのポインターが含まれています。 **IUnknown**します。 キャストすると、各**IUnknown**実際のインターフェイス型へのインターフェイスし、しています。 まず、インターフェイスを照会する必要はありません。  
  
 使用する前に、 **IUnknown**ではないことを確認インターフェイス、 **NULL**します。  
  
##  <a name="ccomunkarray"></a>CComUnkArray::CComUnkArray  
 コンストラクターです。  
  
```
CComUnkArray();
```  
  
### <a name="remarks"></a>コメント  
 保持するコレクションを設定`nMaxSize` **IUnknown**ポインターへのポインターを初期化および**NULL**します。  
  
##  <a name="end"></a>CComUnkArray::end  
 最後に、ポインターを返します**IUnknown**コレクション内のポインター。  
  
```
IUnknown**
    end();
```     
  
### <a name="return-value"></a>戻り値  
 ポインター、 **IUnknown**インターフェイス ポインター。  
  
### <a name="remarks"></a>コメント  
 `CComUnkArray`メソッド**開始**と**エンド**イベントが発生したときに、すべての接続ポイントは、たとえば、ループを使用できます。  
  
 [!code-cpp[NVC_ATL_COM&#44;](../../atl/codesnippet/cpp/ccomunkarray-class_1.cpp)]  
  
##  <a name="getcookie"></a>CComUnkArray::GetCookie  
 関連付けられているクッキーを取得するには、このメソッドを呼び出して、指定された**IUnknown**ポインター。  
  
```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppFind`  
 **IUnknown**ポインター関連 cookie が必要です。  
  
### <a name="return-value"></a>戻り値  
 関連付けられているクッキーを取得、 **IUnknown**ポインター、または一致する場合は 0 **IUnknown**ポインターを検出します。  
  
### <a name="remarks"></a>コメント  
 同じ&1; つ以上のインスタンスが存在**IUnknown**ポインターでは、この関数は、1 つ目の cookie を返します。  
  
##  <a name="getunknown"></a>CComUnkArray::GetUnknown  
 このメソッドを呼び出して取得、 **IUnknown**与えられたクッキーに関連付けられたポインター。  
  
```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCookie`  
 クッキーを関連付けられている**IUnknown**ポインターが必要です。  
  
### <a name="return-value"></a>戻り値  
 返します。、 **IUnknown**ポインター、または一致する cookie が見つからない場合は NULL です。  
  
##  <a name="remove"></a>CComUnkArray::Remove  
 削除するには、このメソッドを呼び出す、 **IUnknown**ポインター、配列に格納します。  
  
```
BOOL Remove(DWORD dwCookie);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCookie`  
 Cookie を参照すること、 **IUnknown**ポインター、配列から削除します。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**場合は、ポインターが削除されると、 **FALSE**それ以外の場合。  
  
## <a name="see-also"></a>関連項目  
 [CComDynamicUnkArray クラス](../../atl/reference/ccomdynamicunkarray-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

