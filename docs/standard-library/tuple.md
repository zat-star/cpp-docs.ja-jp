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
translationtype: Machine Translation
ms.sourcegitcommit: 41b445ceeeb1f37ee9873cb55f62d30d480d8718
ms.openlocfilehash: 7771de57070961751e16294bc966e08843baef4c
ms.lasthandoff: 02/24/2017

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
|[operator==](../standard-library/tuple-operators.md#operator_eq_eq)|`tuple` オブジェクトどうしが等しいかどうかの比較|  
|[operator!=](../standard-library/tuple-operators.md#operator_neq)|`tuple` オブジェクトどうしが等しくないかどうかの比較|  
|[operator<](../standard-library/tuple-operators.md#operator_lt_)|`tuple` オブジェクトどうしの大小関係の比較 (未満)|  
|[operator<=](../standard-library/tuple-operators.md#operator_lt__eq)|`tuple` オブジェクトどうしの大小関係の比較 (以下)|  
|[operator>](../standard-library/tuple-operators.md#operator_gt_)|`tuple` オブジェクトどうしの大小関係の比較 (より大きい)|  
|[operator>=](../standard-library/tuple-operators.md#operator_gt__eq)|`tuple` オブジェクトどうしの大小関係の比較 (以上)|  
  
### <a name="functions"></a>関数  
  
|||  
|-|-|  
|[get](../standard-library/tuple-functions.md#get_function)|`tuple` オブジェクトから要素を取得します。|  
|[make_tuple](../standard-library/tuple-functions.md#make_tuple_function)|要素値から `tuple` を作成します。|  
|[tie](../standard-library/tuple-functions.md#tie_function)|要素参照から `tuple` を作成します。|  
  
## <a name="see-also"></a>関連項目  
 [\<array>](../standard-library/array.md)


