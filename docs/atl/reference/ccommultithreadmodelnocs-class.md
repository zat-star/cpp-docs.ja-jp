---
title: "CComMultiThreadModelNoCS クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CComMultiThreadModelNoCS
- CComMultiThreadModelNoCS
- ATL.CComMultiThreadModelNoCS
dev_langs:
- C++
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModelNoCS class
- threading [ATL]
ms.assetid: 2b3f7a45-fd72-452c-aaf3-ccdaa621c821
caps.latest.revision: 18
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
ms.sourcegitcommit: 1a00023e4d3e31ddb6381e90a50231449b1de18d
ms.openlocfilehash: dd14e5c941da5383dce19e9f7f539bfb9909759f
ms.lasthandoff: 02/28/2017

---
# <a name="ccommultithreadmodelnocs-class"></a>CComMultiThreadModelNoCS クラス
`CComMultiThreadModelNoCS`クリティカル セクションをロックまたはロック解除を行う機能せず、スレッド セーフであるメソッドを変数の値インクリメントおよびデクリメントするために提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CComMultiThreadModelNoCS
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CComMultiThreadModelNoCS::AutoCriticalSection](#autocriticalsection)|クラスを参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)します。|  
|[CComMultiThreadModelNoCS::CriticalSection](#criticalsection)|クラスを参照`CComFakeCriticalSection`します。|  
|[CComMultiThreadModelNoCS::ThreadModelNoCS](#threadmodelnocs)|クラスを参照`CComMultiThreadModelNoCS`します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComMultiThreadModelNoCS::Decrement](#decrement)|(静的)デクリメント、スレッド セーフな方法で指定された変数の値。|  
|[CComMultiThreadModelNoCS::Increment](#increment)|(静的)スレッド セーフな方法で指定された変数の値をインクリメントします。|  
  
## <a name="remarks"></a>コメント  
 `CComMultiThreadModelNoCS`ような[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)を提供するスレッド セーフな方法インクリメントおよびデクリメントするための変数です。 ただし、を介して、クリティカル セクション クラスを参照する`CComMultiThreadModelNoCS`などのメソッド`Lock`と`Unlock`が何も行いません。  
  
 通常、使用して`CComMultiThreadModelNoCS`を通じて、 `ThreadModelNoCS` `typedef`名。 これは、`typedef`で定義された`CComMultiThreadModelNoCS`、 `CComMultiThreadModel`、および[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)します。  
  
> [!NOTE]
>  グローバル`typedef`名[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)と[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)が参照されていない`CComMultiThreadModelNoCS`します。  
  
 他に、 `ThreadModelNoCS`、`CComMultiThreadModelNoCS`定義`AutoCriticalSection`と`CriticalSection`です。 これら後者の&2; つ`typedef`名前参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)を取得および解放、クリティカル セクションに関連付けられている、空のメソッドを提供します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="a-nameautocriticalsectiona--ccommultithreadmodelnocsautocriticalsection"></a><a name="autocriticalsection"></a>CComMultiThreadModelNoCS::AutoCriticalSection  
 使用する場合`CComMultiThreadModelNoCS`、`typedef`名`AutoCriticalSection`クラスを参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)します。  
  
```
typedef CComFakeCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>コメント  
 `CComFakeCriticalSection`クリティカル セクションの管轄外のメソッドは、何も行いません。  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)もの定義を含む`AutoCriticalSection`します。 次の表は、スレッド処理モデル クラスとによって参照されるクリティカル セクション クラス間のリレーションシップを示しています`AutoCriticalSection`:。  
  
|定義されたクラス|参照されるクラス|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComAutoCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
  
 他に、 `AutoCriticalSection`、使用することができます、`typedef`名[CriticalSection](#criticalsection)します。 指定しないでください`AutoCriticalSection`グローバル オブジェクトまたは静的クラス メンバーの場合は、CRT のスタートアップ コードを削除します。  
  
### <a name="example"></a>例  
 参照してください[CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)します。  
  
##  <a name="a-namecriticalsectiona--ccommultithreadmodelnocscriticalsection"></a><a name="criticalsection"></a>CComMultiThreadModelNoCS::CriticalSection  
 使用する場合`CComMultiThreadModelNoCS`、`typedef`名`CriticalSection`クラスを参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)します。  
  
```
typedef CComFakeCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>コメント  
 `CComFakeCriticalSection`クリティカル セクションの管轄外のメソッドは、何も行いません。  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)もの定義を含む`CriticalSection`します。 次の表は、スレッド処理モデル クラスとによって参照されるクリティカル セクション クラス間のリレーションシップを示しています`CriticalSection`:。  
  
|定義されたクラス|参照されるクラス|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
  
 他に、 `CriticalSection`、使用することができます、`typedef`名前`AutoCriticalSection`します。 指定しないでください`AutoCriticalSection`グローバル オブジェクトまたは静的クラス メンバーの場合は、CRT のスタートアップ コードを削除します。  
  
### <a name="example"></a>例  
 参照してください[CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)します。  
  
##  <a name="a-namedecrementa--ccommultithreadmodelnocsdecrement"></a><a name="decrement"></a>CComMultiThreadModelNoCS::Decrement  
 この静的関数は、Win32 関数を呼び出して[InterlockedDecrement](http://msdn.microsoft.com/library/windows/desktop/ms683580)、指す変数の値をデクリメント`p`します。  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 [in]デクリメントする変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 減算の結果が 0 で、 `Decrement` 0 を返します。 減算の結果が&0; 以外の場合、戻り値は&0; 以外の値もですが、減算の結果が等しくない場合があります。  
  
### <a name="remarks"></a>コメント  
 **InterlockedDecrement**複数のスレッドが同時にこの変数を使用することを防止します。  
  
##  <a name="a-nameincrementa--ccommultithreadmodelnocsincrement"></a><a name="increment"></a>CComMultiThreadModelNoCS::Increment  
 この静的関数は、Win32 関数を呼び出して[InterlockedIncrement](http://msdn.microsoft.com/library/windows/desktop/ms683614)が指す変数の値をインクリメントする`p`です。  
  
```
static ULONG WINAPI Increment(LPLONG p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 [in]インクリメントする変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 インクリメントの結果が 0、**インクリメント**0 を返します。 インクリメントの結果が&0; 以外の場合、戻り値は&0; 以外の値もですが、増分の結果が等しくない場合があります。  
  
### <a name="remarks"></a>コメント  
 **InterlockedIncrement**複数のスレッドが同時にこの変数を使用することを防止します。  
  
##  <a name="a-namethreadmodelnocsa--ccommultithreadmodelnocsthreadmodelnocs"></a><a name="threadmodelnocs"></a>CComMultiThreadModelNoCS::ThreadModelNoCS  
 使用する場合`CComMultiThreadModelNoCS`、`typedef`名`ThreadModelNoCS`単に参照`CComMultiThreadModelNoCS`します。  
  
```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```  
  
### <a name="remarks"></a>コメント  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)もの定義を含む`ThreadModelNoCS`します。 次の表は、スレッド処理モデル クラスとによって参照されるクラス間のリレーションシップを示しています`ThreadModelNoCS`:。  
  
|定義されたクラス|参照されるクラス|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
  
 定義`ThreadModelNoCS`で`CComMultiThreadModelNoCS`との対称性を提供`CComMultiThreadModel`と`CComSingleThreadModel`です。 たとえば、サンプル コードを`CComMultiThreadModel::AutoCriticalSection`、次の宣言`typedef`:  
  
 [!code-cpp[NVC_ATL_COM&#37;](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]  
  
 指定されたクラスに関係なく`ThreadModel`(よう`CComMultiThreadModelNoCS`)、`_ThreadModel`それに応じて解決します。  
  
### <a name="example"></a>例  
 参照してください[CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
