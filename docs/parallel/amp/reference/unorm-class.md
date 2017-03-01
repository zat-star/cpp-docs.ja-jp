---
title: "unorm クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::unorm
- amp/Concurrency::graphics::unorm
dev_langs:
- C++
ms.assetid: bc30bd20-6452-4d5f-9158-3b11c4c16ed2
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: aae5de80bed3b2d3d5c15285c2d12f2f6771a251
ms.lasthandoff: 02/24/2017

---
# <a name="unorm-class"></a>unorm クラス
Unorm 数を表します。 各要素は、浮動小数点数を [0.0 f, 1.0 f] の範囲内です。  
  
## <a name="syntax"></a>構文  
  
```  
class unorm;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[unorm コンス トラクター](#ctor)|オーバーロードされます。 既定のコンストラクター 0.0 f を初期化します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|unorm::operator--演算子||  
|unorm::operator float 演算子|変換演算子。 Unorm 数に変換、浮動小数点値。|  
|unorm::operator * = 演算子||  
|unorm::operator/= 演算子||  
|unorm::operator:operator++ 演算子||  
|unorm::operator + = 演算子||  
|unorm::operator = 演算子||  
|unorm::operator-= 演算子||  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `unorm`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amp_short_vectors.h  
  
 **Namespace:** concurrency::graphics  
  
##  <a name="a-namectora-unorm"></a><a name="ctor"></a>unorm 

 既定のコンストラクター 0.0 f を初期化します。  
  
```  
unorm(
    void) restrict(amp,
    cpu);

 
explicit unorm(
    float _V) restrict(amp,
    cpu);

 
explicit unorm(
    unsigned int _V) restrict(amp,
    cpu);

 
explicit unorm(
    int _V) restrict(amp,
    cpu);

 
explicit unorm(
    double _V) restrict(amp,
    cpu);

 
unorm(
    const unorm& _Other) restrict(amp,
    cpu);

 
inline explicit unorm(
    const norm& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_V`  
 初期化するために使用する値。  
  
 `_Other`  
 初期化に使用される標準オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [Concurrency::graphics Namespace](concurrency-graphics-namespace.md)

