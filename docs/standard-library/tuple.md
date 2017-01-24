---
title: "&lt; tuple &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<tuple>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "タプル ヘッダー [TR1]"
ms.assetid: e4ef5c2d-318b-44f6-8bce-fce4ecd796a3
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt; tuple &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

テンプレートを定義 `tuple` あり、そのインスタンスは、さまざまな種類のオブジェクトを格納します。  
  
## <a name="syntax"></a>構文  
  
```  
#include <tuple>  
```  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[組](../standard-library/tuple-class.md)|要素の固定長シーケンスをラップします。|  
|[tuple_element クラス](../standard-library/tuple-element-class-tuple.md)|`tuple` 要素の型をラップします。|  
|[tuple_size クラス](../standard-library/tuple-size-class-tuple.md)|`tuple` の要素数をラップします。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 = =](../Topic/%3Ctuple%3E%20operators.md#operator_eq_eq)|比較の `tuple` オブジェクトと等しい|  
|[operator! =](../Topic/%3Ctuple%3E%20operators.md#operator_neq)|比較の `tuple` オブジェクト、等しくないです。|  
|[演算子 <](../Topic/%3Ctuple%3E%20operators.md#operator_lt_)|比較の `tuple` オブジェクトより小さい|  
|[operator < =](../Topic/%3Ctuple%3E%20operators.md#operator_lt__eq)|比較の `tuple` 以下のオブジェクト|  
|[演算子 >](../Topic/%3Ctuple%3E%20operators.md#operator_gt_)|比較の `tuple` より大きいオブジェクト|  
|[operator > =](../Topic/%3Ctuple%3E%20operators.md#operator_gt__eq)|比較の `tuple` 以上のオブジェクト|  
  
### <a name="functions"></a>関数  
  
|||  
|-|-|  
|[取得](../Topic/%3Ctuple%3E%20functions.md#get_function)|`tuple` オブジェクトから要素を取得します。|  
|[make_tuple](../Topic/%3Ctuple%3E%20functions.md#make_tuple_function)|により、 `tuple` 要素の値からです。|  
|[同順位](../Topic/%3Ctuple%3E%20functions.md#tie_function)|により、 `tuple` 要素の参照から。|  
  
## <a name="see-also"></a>参照  
 [\< 配列>](../standard-library/array.md)

