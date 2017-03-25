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
- unorm
- AMP_SHORT_VECTORS/unorm
- AMP_SHORT_VECTORS/Concurrency::graphics::unorm Constructor
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 6817568b7dc111776033e935fd2ba3ad5dc4a69a
ms.lasthandoff: 03/17/2017

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
|unorm::operator--||  
|unorm::operator float|変換演算子。 Unorm 数に変換、浮動小数点値。|  
|unorm::operator * =||  
|unorm::operator/=||  
|unorm::operator + +||  
|unorm::operator + = 演算子||  
|unorm::operator =||  
|unorm::operator =||  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `unorm`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amp_short_vectors.h  
  
 **Namespace:** concurrency::graphics  
  
##  <a name="ctor"></a>unorm 

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
 [Concurrency::graphics 名前空間](concurrency-graphics-namespace.md)

