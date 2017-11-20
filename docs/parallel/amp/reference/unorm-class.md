---
title: "unorm クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unorm
- AMP_SHORT_VECTORS/unorm
- AMP_SHORT_VECTORS/Concurrency::graphics::unorm Constructor
dev_langs: C++
ms.assetid: bc30bd20-6452-4d5f-9158-3b11c4c16ed2
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5aa633b67bcd5b313faa475d911300635d727f5b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="unorm-class"></a>unorm クラス
Unorm 数を表します。 各要素は、浮動小数点 [0.0 f, 1.0f] の範囲の数。  
  
## <a name="syntax"></a>構文  
  
```  
class unorm;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[unorm コンス トラクター](#ctor)|オーバーロードされます。 既定のコンストラクター 0.0f を初期化します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|unorm::operator--||  
|unorm::operator float|変換演算子です。 Unorm 数、浮動小数点に変換する値をポイントします。|  
|unorm::operator * =||  
|unorm::operator/=||  
|+ + unorm::operator||  
|unorm::operator + =||  
|unorm::operator =||  
|unorm::operator =||  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `unorm`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amp_short_vectors.h  
  
 **Namespace:** concurrency::graphics  
  
##  <a name="ctor"></a>unorm 

 既定のコンストラクター 0.0f を初期化します。  
  
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
 初期化するために使用される norm オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [Concurrency::graphics 名前空間](concurrency-graphics-namespace.md)
