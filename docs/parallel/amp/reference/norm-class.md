---
title: "norm クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::norm
dev_langs:
- C++
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
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
ms.openlocfilehash: 8ff5a99136a75d17d914783496205f1dd1eb4a06
ms.lasthandoff: 02/24/2017

---
# <a name="norm-class"></a>norm クラス
Norm 数を表します。 各要素は、浮動小数点数を範囲内の [-1.0 f、1.0 f] です。  
  
## <a name="syntax"></a>構文  
  
```  
class norm;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[norm コンス トラクター](#ctor)|オーバーロードされます。 既定のコンストラクター 0.0 f を初期化します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|norm::operator 演算子||  
|norm::operator--演算子||  
|norm::operator float 演算子|変換演算子。 Norm 数、浮動小数点に変換する値をポイントします。|  
|norm::operator * = 演算子||  
|norm::operator/= 演算子||  
|norm::operator:operator++ 演算子||  
|norm::operator + = 演算子||  
|norm::operator = 演算子||  
|norm::operator-= 演算子||  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `norm`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amp_short_vectors.h  
  
 **Namespace:** concurrency::graphics  
  
##  <a name="a-namectora-norm"></a><a name="ctor"></a>norm 

 既定のコンストラクター 0.0 f を初期化します。  
  
```  
norm(
    void) restrict(amp,
    cpu);

 
explicit norm(
    float _V) restrict(amp,
    cpu);

 
explicit norm(
    unsigned int _V) restrict(amp,
    cpu);

 
explicit norm(
    int _V) restrict(amp,
    cpu);

 
explicit norm(
    double _V) restrict(amp,
    cpu);

 
norm(
    const norm& _Other) restrict(amp,
    cpu);

 
norm(
    const unorm& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_V`  
 初期化するために使用する値。  
  
 `_Other`  
 初期化するために使用するオブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [Concurrency::graphics Namespace](concurrency-graphics-namespace.md)

