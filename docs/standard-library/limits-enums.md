---
title: "&lt;limits&gt; 列挙型 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- limits/std::float_denorm_style
- limits/std::float_round_style
ms.assetid: c86680a2-ba97-4ed9-8c20-a448857d7dc5
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: a776ccd0299c3acc43763a381ce337c67bc6c134
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ltlimitsgt-enums"></a>&lt;limits&gt; 列挙型
|||  
|-|-|  
|[float_denorm_style](#float_denorm_style)|[float_round_style](#float_round_style)|  
  
##  <a name="float_denorm_style"></a>  float_denorm_style 列挙型  
 この列挙体では、小さすぎて、正規化された値としては表現できない非正規化された浮動小数点値を表現するために、実装で選択できるさまざまなメソッドを記述します。  
  
```
enum float_denorm_style {
    denorm_indeterminate = -1,
    denorm_absent = 0,
    denorm_present = 1    };
```  
  
### <a name="return-value"></a>戻り値  
 この列挙型は以下を返します。  
  
- **denorm_indeterminate**: 変換時に非正規化形式の有無を特定できない場合。  
  
- **denorm_absent**: 非正規化形式が存在しない場合。  
  
- **denorm_absent**: 非正規化形式が存在する場合。  
  
### <a name="example"></a>例  
  この列挙型の値にアクセスする例については、「[numeric_limits::has_denorm](../standard-library/numeric-limits-class.md#has_denorm)」を参照してください。  
  
##  <a name="float_round_style"></a>  float_round_style 列挙型  
 この列挙体では、浮動小数点値を整数値に丸めるために、実装で選択できるさまざまなメソッドを記述します。  
  
```
enum float_round_style {    
    round_indeterminate = -1,
    round_toward_zero = 0,
    round_to_nearest = 1,
    round_toward_infinity = 2,
    round_toward_neg_infinity = 3    };
```  
  
### <a name="return-value"></a>戻り値  
 この列挙型は以下を返します。  
  
- **round_indeterminate**: 丸め処理を行う方法を特定できない場合。  
  
- **round_toward_zero**: ゼロに向かって丸める場合。  
  
- **round_to_nearest**: 最も近い整数に丸める場合。  
  
- **round_toward_infinity**: ゼロから離れるように丸める場合。  
  
- **round_toward_neg_infinity**: より負の方向の整数に丸める場合。  
  
### <a name="example"></a>例  
  この列挙型の値にアクセスする例については、「[numeric_limits::round_style](../standard-library/numeric-limits-class.md#round_style)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [\<limits>](../standard-library/limits.md)



