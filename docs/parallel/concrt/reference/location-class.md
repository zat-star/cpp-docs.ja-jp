---
title: "location クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::location
dev_langs:
- C++
helpviewer_keywords:
- location class
ms.assetid: c3289f51-5bf1-4dff-a18d-d0dab8e5d9c7
caps.latest.revision: 10
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 1a404f44600addcbf332fabcfc19a7b48dab0c81
ms.lasthandoff: 02/24/2017

---
# <a name="location-class"></a>location クラス
ハードウェアの物理位置の抽象化です。  
  
## <a name="syntax"></a>構文  
  
```
class location;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[コンス トラクターの場所](#ctor)|オーバーロードされます。 `location` オブジェクトを構築します。|  
|[~ location デストラクター](#dtor)|`location` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[現在のメソッド](#current)|返します。、`location`呼び出し元のスレッドを実行する最も特定の場所を表すオブジェクト。|  
|[from_numa_node メソッド](#from_numa_node)|返します。、`location`を指定した NUMA ノードを表すオブジェクト。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator! = 演算子](#operator_neq)|2 つあるかどうかを決定`location`オブジェクトが別の場所を表します。|  
|[operator = 演算子](#operator_eq)|別の内容を割り当てます`location`オブジェクトをこのオブジェクトにします。|  
|[operator = 演算子](#operator_eq_eq)|2 つあるかどうかを決定`location`オブジェクトが同じ場所を表します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `location`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namedtora-location"></a><a name="dtor"></a>~ の場所 

 `location` オブジェクトを破棄します。  
  
```
~location();
```  
  
##  <a name="a-namecurrenta-current"></a><a name="current"></a>現在の 

 返します。、`location`呼び出し元のスレッドを実行する最も特定の場所を表すオブジェクト。  
  
```
static location __cdecl current();
```  
  
### <a name="return-value"></a>戻り値  
 ほとんどの特定の場所を表す場所、呼び出し元のスレッドが実行しています。  
  
##  <a name="a-namefromnumanodea-fromnumanode"></a><a name="from_numa_node"></a>from_numa_node 

 返します。、`location`を指定した NUMA ノードを表すオブジェクト。  
  
```
static location __cdecl from_numa_node(unsigned short _NumaNodeNumber);
```  
  
### <a name="parameters"></a>パラメーター  
 `_NumaNodeNumber`  
 場所を構築する NUMA ノードの数。  
  
### <a name="return-value"></a>戻り値  
 指定された NUMA ノードを表す場所、`_NumaNodeNumber`パラメーター。  
  
##  <a name="a-namectora-location"></a><a name="ctor"></a>場所 

 `location` オブジェクトを構築します。  
  
```
location();

location(
    const location& _Src);

location(
    T _LocationType,
    unsigned int _Id,
    unsigned int _BindingId = 0,
    _Inout_opt_ void* _PBinding = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Src`  
 `_LocationType`  
 `_Id`  
 `_BindingId`  
 `_PBinding`  
  
### <a name="remarks"></a>コメント  
 構築された既定の場所は、全体としてシステムを表します。  
  
##  <a name="a-nameoperatorneqa-operator"></a><a name="operator_neq"></a>operator! = 

 2 つあるかどうかを決定`location`オブジェクトが別の場所を表します。  
  
```
bool operator!= (const location& _Rhs) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Rhs`  
  
### <a name="return-value"></a>戻り値  
 `true`2 つの場所が異なる場合、`false`それ以外の場合。  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>演算子 = 

 別の内容を割り当てます`location`オブジェクトをこのオブジェクトにします。  
  
```
location& operator= (const location& _Rhs);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Rhs`  
 ソース `location` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="a-nameoperatoreqeqa-operator"></a><a name="operator_eq_eq"></a>演算子 = = 

 2 つあるかどうかを決定`location`オブジェクトが同じ場所を表します。  
  
```
bool operator== (const location& _Rhs) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Rhs`  
  
### <a name="return-value"></a>戻り値  
 `true`2 つの場所は同じですが場合、および`false`それ以外の場合。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)

