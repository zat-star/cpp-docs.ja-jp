---
title: "CComDynamicUnkArray クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::Add
- ATLCOM/ATL::CComDynamicUnkArray::begin
- ATLCOM/ATL::CComDynamicUnkArray::clear
- ATLCOM/ATL::CComDynamicUnkArray::end
- ATLCOM/ATL::CComDynamicUnkArray::GetAt
- ATLCOM/ATL::CComDynamicUnkArray::GetCookie
- ATLCOM/ATL::CComDynamicUnkArray::GetSize
- ATLCOM/ATL::CComDynamicUnkArray::GetUnknown
- ATLCOM/ATL::CComDynamicUnkArray::Remove
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- CComDynamicUnkArray class
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 69fc2c9dbb86f88c85461e765182fd88050521e9
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ccomdynamicunkarray-class"></a>CComDynamicUnkArray クラス
このクラスの配列を格納する**IUnknown**ポインター。  
  
## <a name="syntax"></a>構文  
  
```
class CComDynamicUnkArray
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComDynamicUnkArray::CComDynamicUnkArray](#ccomdynamicunkarray)|コンストラクターです。 コレクションの値を初期化**NULL**とコレクションのサイズを&0; にします。|  
|[CComDynamicUnkArray:: ~ CComDynamicUnkArray](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComDynamicUnkArray::Add](#add)|追加するには、このメソッドを呼び出して、`IUnknown`配列へのポインター。|  
|[CComDynamicUnkArray::begin](#begin)|最初のポインターを返します`IUnknown`コレクション内のポインター。|  
|[CComDynamicUnkArray::clear](#clear)|配列が空にします。|  
|[CComDynamicUnkArray::end](#end)|最後に、ポインターを返します**IUnknown**コレクション内のポインター。|  
|[CComDynamicUnkArray::GetAt](#getat)|指定したインデックス位置にある要素を取得します。|  
|[CComDynamicUnkArray::GetCookie](#getcookie)|関連付けられているクッキーを取得するには、このメソッドを呼び出して、指定された**IUnknown**ポインター。|  
|[CComDynamicUnkArray::GetSize](#getsize)|配列の長さを返します。|  
|[CComDynamicUnkArray::GetUnknown](#getunknown)|このメソッドを呼び出して取得、 **IUnknown**与えられたクッキーに関連付けられたポインター。|  
|[CComDynamicUnkArray::Remove](#remove)|削除するには、このメソッドを呼び出す、 **IUnknown**ポインター、配列に格納します。|  
  
## <a name="remarks"></a>コメント  
 **CComDynamicUnkArray**の動的に割り当てられた配列を保持**IUnknown**ポインター、接続のインターフェイスが各をポイントします。 **CComDynamicUnkArray**をパラメーターとして使用できる、 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)テンプレート クラス。  
  
 **CComDynamicUnkArray**メソッド[開始](#begin)と[エンド](#end)(たとえば、イベントが発生したときに) すべてのコネクション ポイントをループするために使用できます。  
  
 参照してください[オブジェクトのコネクション ポイントの追加](../../atl/adding-connection-points-to-an-object.md)接続の作成を自動化することの詳細については、プロキシをポイントします。  
  
> [!NOTE]
> **注**クラス**CComDynamicUnkArray**によって使用される、**クラスの追加**コネクション ポイントを持つコントロールを作成するときにウィザード。 コネクション ポイントの数を手動で指定する場合は、変更からの参照**CComDynamicUnkArray**に`CComUnkArray<` *n* `>`ここで、 *n*のために必要な接続ポイントの数です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="add"></a>CComDynamicUnkArray::Add  
 追加するには、このメソッドを呼び出して、 **IUnknown**配列へのポインター。  
  
```
DWORD Add(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 **IUnknown**配列に追加へのポインター。  
  
### <a name="return-value"></a>戻り値  
 新しく追加されたポインターに関連付けられているクッキーを返します。  
  
##  <a name="begin"></a>CComDynamicUnkArray::begin  
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
  
##  <a name="clear"></a>CComDynamicUnkArray::clear  
 配列が空にします。  
  
```
void clear();
```  
  
##  <a name="ccomdynamicunkarray"></a>CComDynamicUnkArray::CComDynamicUnkArray  
 コンストラクターです。  
  
```
CComDynamicUnkArray();
```  
  
### <a name="remarks"></a>コメント  
 コレクションのサイズを&0; に設定し、値を初期化**NULL**します。 デストラクターは、必要に応じて、コレクションを解放します。  
  
##  <a name="dtor"></a>CComDynamicUnkArray:: ~ CComDynamicUnkArray  
 デストラクターです。  
  
```
~CComDynamicUnkArray();
```  
  
### <a name="remarks"></a>コメント  
 クラスのコンス トラクターによって割り当てられたリソースを解放します。  
  
##  <a name="end"></a>CComDynamicUnkArray::end  
 最後に、ポインターを返します**IUnknown**コレクション内のポインター。  
  
```
IUnknown**
    end();
```     
  
### <a name="return-value"></a>戻り値  
 ポインター、 **IUnknown**インターフェイス ポインター。  
  
##  <a name="getat"></a>CComDynamicUnkArray::GetAt  
 指定したインデックス位置にある要素を取得します。  
  
```
IUnknown* GetAt(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 取得する要素のインデックス。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)インターフェイスです。  
  
##  <a name="getcookie"></a>CComDynamicUnkArray::GetCookie  
 関連付けられているクッキーを取得するには、このメソッドを呼び出して、指定された**IUnknown**ポインター。  
  
```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppFind`  
 **IUnknown**ポインター関連 cookie が必要です。  
  
### <a name="return-value"></a>戻り値  
 関連付けられているクッキーを取得、 **IUnknown**ポインター、または一致する場合は&0; を**IUnknown**ポインターを検出します。  
  
### <a name="remarks"></a>コメント  
 同じ&1; つ以上のインスタンスが存在**IUnknown**ポインターでは、この関数は、1 つ目の cookie を返します。  
  
##  <a name="getsize"></a>CComDynamicUnkArray::GetSize  
 配列の長さを返します。  
  
```
int GetSize() const;
```  
  
### <a name="return-value"></a>戻り値  
 配列の長さ。  
  
##  <a name="getunknown"></a>CComDynamicUnkArray::GetUnknown  
 このメソッドを呼び出して取得、 **IUnknown**与えられたクッキーに関連付けられたポインター。  
  
```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCookie`  
 クッキーを関連付けられている**IUnknown**ポインターが必要です。  
  
### <a name="return-value"></a>戻り値  
 返します。、 **IUnknown**ポインター、または一致する cookie が見つからない場合は NULL です。  
  
##  <a name="remove"></a>CComDynamicUnkArray::Remove  
 削除するには、このメソッドを呼び出す、 **IUnknown**ポインター、配列に格納します。  
  
```
BOOL Remove(DWORD dwCookie);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCookie`  
 Cookie を参照すること、 **IUnknown**ポインター、配列から削除します。  
  
### <a name="return-value"></a>戻り値  
 マウス ポインターが削除されたかどうかは TRUE を返しますそれ以外の場合は FALSE。  
  
## <a name="see-also"></a>関連項目  
 [CComUnkArray クラス](../../atl/reference/ccomunkarray-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

