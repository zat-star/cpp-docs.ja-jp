---
title: "CComSingleThreadModel クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComSingleThreadModel::CriticalSection
- ATLBASE/ATL::CComSingleThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComSingleThreadModel::Decrement
- ATLBASE/ATL::CComSingleThreadModel::Increment
dev_langs:
- C++
helpviewer_keywords:
- single-threaded applications
- CComSingleThreadModel class
- single-threaded applications, ATL
ms.assetid: e5dc30c7-405a-4ba4-8ae9-51937243fce8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: ff5d8d2ced1d6fe0196888d8c746844ace8307f8
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ccomsinglethreadmodel-class"></a>CComSingleThreadModel クラス
このクラスは、変数の値、インクリメントおよびデクリメントするためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CComSingleThreadModel
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CComSingleThreadModel::AutoCriticalSection](#autocriticalsection)|クラスを参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)します。|  
|[CComSingleThreadModel::CriticalSection](#criticalsection)|クラスを参照`CComFakeCriticalSection`します。|  
|[CComSingleThreadModel::ThreadModelNoCS](#threadmodelnocs)|参照`CComSingleThreadModel`します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComSingleThreadModel::Decrement](#decrement)|デクリメント指定された変数の値。 この実装は、スレッド セーフではありません。|  
|[CComSingleThreadModel::Increment](#increment)|指定された変数の値をインクリメントします。 この実装は、スレッド セーフではありません。|  
  
## <a name="remarks"></a>コメント  
 `CComSingleThreadModel`インクリメントおよびデクリメントするため、変数の値に対応するメソッドを提供します。 異なり[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)、これらのメソッドがスレッド セーフではありません。  

 通常、使用して`CComSingleThreadModel`2 つのいずれかを通して`typedef`名か、 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)または[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)します。 各によって参照されるクラス`typedef`次の表に示すように使用すると、スレッド処理モデルによって異なります。  

  
|typedef|シングル スレッド モデル|アパートメント スレッド モデル|フリー スレッド モデル|  
|-------------|----------------------------|-------------------------------|--------------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S= `CComSingleThreadModel`;M =`CComMultiThreadModel`  
  
 `CComSingleThreadModel`3 つの定義自体`typedef`名。 `ThreadModelNoCS`参照`CComSingleThreadModel`します。 `AutoCriticalSection``CriticalSection`クラスを参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)を取得し、クリティカル セクションの所有権を解放するに関連付けられている、空のメソッドを提供します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="autocriticalsection"></a>CComSingleThreadModel::AutoCriticalSection  
 使用する場合`CComSingleThreadModel`、`typedef`名`AutoCriticalSection`クラスを参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)します。  
  
```
typedef CComFakeCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>コメント  
 `CComFakeCriticalSection`クリティカル セクションの管轄外のメソッドは、何も行いません。  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)の定義を含む`AutoCriticalSection`します。 次の表は、スレッド処理モデル クラスとによって参照されるクリティカル セクション クラス間のリレーションシップを示しています`AutoCriticalSection`:。  
  
|定義されたクラス|参照されるクラス|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComAutoCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 他に、 `AutoCriticalSection`、使用することができます、`typedef`名[CriticalSection](#criticalsection)します。 指定しないでください`AutoCriticalSection`グローバル オブジェクトまたは静的クラス メンバーの場合は、CRT のスタートアップ コードを削除します。  
  
### <a name="example"></a>例  
 参照してください[CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)します。  
  
##  <a name="criticalsection"></a>CComSingleThreadModel::CriticalSection  
 使用する場合`CComSingleThreadModel`、`typedef`名`CriticalSection`クラスを参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)します。  
  
```
typedef CComFakeCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>コメント  
 `CComFakeCriticalSection`クリティカル セクションの管轄外のメソッドは、何も行いません。  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)の定義を含む`CriticalSection`します。 次の表は、スレッド処理モデル クラスとによって参照されるクリティカル セクション クラス間のリレーションシップを示しています`CriticalSection`:。  
  
|定義されたクラス|参照されるクラス|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 他に、 `CriticalSection`、使用することができます、`typedef`名[AutoCriticalSection](#autocriticalsection)します。 指定しないでください`AutoCriticalSection`グローバル オブジェクトまたは静的クラス メンバーの場合は、CRT のスタートアップ コードを削除します。  
  
### <a name="example"></a>例  
 参照してください[CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)します。  
  
##  <a name="decrement"></a>CComSingleThreadModel::Decrement  
 この静的関数デクリメント、変数の値が指す`p`します。  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 [in]デクリメントする変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 減算の結果です。  
  
##  <a name="increment"></a>CComSingleThreadModel::Increment  
 この静的関数デクリメント、変数の値が指す`p`します。  
  
```
static ULONG WINAPI Increment(LPLONG p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 [in]インクリメントする変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 増分の結果です。  
  
##  <a name="threadmodelnocs"></a>CComSingleThreadModel::ThreadModelNoCS  
 使用する場合`CComSingleThreadModel`、`typedef`名`ThreadModelNoCS`単に参照`CComSingleThreadModel`します。  
  
```
typedef CComSingleThreadModel ThreadModelNoCS;
```  
  
### <a name="remarks"></a>コメント  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)の定義を含む`ThreadModelNoCS`します。 次の表は、スレッド処理モデル クラスとによって参照されるクラス間のリレーションシップを示しています`ThreadModelNoCS`:。  
  
|定義されたクラス|参照されるクラス|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
  
### <a name="example"></a>例  
 参照してください[CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

