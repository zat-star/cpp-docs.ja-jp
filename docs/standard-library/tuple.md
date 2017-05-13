---
title: '&lt;tuple&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <tuple>
dev_langs:
- C++
helpviewer_keywords:
- tuple header
ms.assetid: e4ef5c2d-318b-44f6-8bce-fce4ecd796a3
caps.latest.revision: 20
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 212b2b5af678bd39b4ecc7d6622c71db20db5a26
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="lttuplegt"></a>&lt;tuple&gt;
さまざまな型のオブジェクトを保持するインスタンスを持つテンプレート `tuple` を定義します。  
  
## <a name="syntax"></a>構文  
  
```  
#include <tuple>  
```  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[tuple](../standard-library/tuple-class.md)|要素の固定長シーケンスをラップします。|  
|[tuple_element クラス](../standard-library/tuple-element-class-tuple.md)|`tuple` 要素の型をラップします。|  
|[tuple_size クラス](../standard-library/tuple-size-class-tuple.md)|`tuple` の要素数をラップします。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator==](../standard-library/tuple-operators.md#op_eq_eq)|`tuple` オブジェクトどうしが等しいかどうかの比較|  
|[operator!=](../standard-library/tuple-operators.md#op_neq)|`tuple` オブジェクトどうしが等しくないかどうかの比較|  
|[operator<](../standard-library/tuple-operators.md#op_lt)|`tuple` オブジェクトどうしの大小関係の比較 (未満)|  
|[operator<=](../standard-library/tuple-operators.md#op_lt_eq)|`tuple` オブジェクトどうしの大小関係の比較 (以下)|  
|[operator>](../standard-library/tuple-operators.md#op_gt)|`tuple` オブジェクトどうしの大小関係の比較 (より大きい)|  
|[operator>=](../standard-library/tuple-operators.md#op_gt_eq)|`tuple` オブジェクトどうしの大小関係の比較 (以上)|  
  
### <a name="functions"></a>関数  
  
|||  
|-|-|  
|[get](../standard-library/tuple-functions.md#get)|`tuple` オブジェクトから要素を取得します。|  
|[make_tuple](../standard-library/tuple-functions.md#make_tuple)|要素値から `tuple` を作成します。|  
|[tie](../standard-library/tuple-functions.md#tie)|要素参照から `tuple` を作成します。|  
  
## <a name="see-also"></a>関連項目  
 [\<array>](../standard-library/array.md)


