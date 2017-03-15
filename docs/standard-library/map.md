---
title: '&lt;map&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::<map>
- std.<map>
- <map>
dev_langs:
- C++
helpviewer_keywords:
- map header
ms.assetid: bbf76680-7362-456e-88fa-ecda93561b6a
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: fad398e9f18c2f45de7e071be464e3eff2e9243e
ms.lasthandoff: 02/24/2017

---
# <a name="ltmapgt"></a>&lt;map&gt;
コンテナーのテンプレート クラス map と multimap およびサポート テンプレートを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
#include <map>  
  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="operators"></a>演算子  
  
|map バージョン|multimap バージョン|説明|  
|-----------------|----------------------|-----------------|  
|[operator!= (map)](../standard-library/map-operators.md#operator_neq)|[operator!= (multimap)](../standard-library/map-operators.md#operator_neq)|演算子の左側の map または multimap オブジェクトが右側の map または multimap オブジェクトと等しくないかどうかをテストします。|  
|[operator< (map)](../standard-library/map-operators.md#operator_eq_eq)|[operator< (multimap)](../standard-library/map-operators.md#operator_eq_eq)|演算子の左側の map または multimap オブジェクトが右側の map または multimap オブジェクトより小さいかどうかをテストします。|  
|[operator<= (map)](../standard-library/map-operators.md#operator_lt_)|[operator\<= (multimap)](../standard-library/map-operators.md#operator_lt_)|演算子の左側の map または multimap オブジェクトが右側の map または multimap オブジェクト以下かどうかをテストします。|  
|[operator== (map)](../standard-library/map-operators.md#operator_lt__eq)|[operator== (multimap)](../standard-library/map-operators.md#operator_lt__eq)|演算子の左側の map または multimap オブジェクトが右側の map または multimap オブジェクトと等しいかどうかをテストします。|  
|[operator> (map)](../standard-library/map-operators.md#operator_gt_)|[operator> (multimap)](../standard-library/map-operators.md#operator_gt_)|演算子の左側の map または multimap オブジェクトが右側の map または multimap オブジェクトより大きいかどうかを調べます。|  
|[operator>= (map)](../standard-library/map-operators.md#operator_gt__eq)|[operator>= (multimap)](../standard-library/map-operators.md#operator_gt__eq)|演算子の左側の map または multimap オブジェクトが右側の map または multimap オブジェクト以上であるかどうかをテストします。|  
  
### <a name="specialized-template-functions"></a>特殊テンプレート関数  
  
|map バージョン|multimap バージョン|説明|  
|-----------------|----------------------|-----------------|  
|[swap (map)](../standard-library/map-functions.md#swap)|[swap (multimap)](../standard-library/map-functions.md#swap)|2 個の map または multimaps の要素を交換します。|  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[value_compare クラス](../standard-library/value-compare-class-map.md)|要素のキーの値を比較し要素のマップ内の相対順序を決定して、マップの要素を比較できる関数オブジェクトを提供します。|  
|[map クラス](../standard-library/map-class.md)|各要素にデータを自動的に並べる一意キーを持つコレクションからデータを格納および取得するために使用します。|  
|[multimap クラス](../standard-library/multimap-class.md)|各要素にデータを自動的に並べるキー (一意の値である必要はありません) を持つコレクションからデータを格納および取得するために使用します。|  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)




