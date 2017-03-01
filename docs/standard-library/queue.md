---
title: '&lt;queue&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::<queue>
- std.<queue>
- <queue>
dev_langs:
- C++
helpviewer_keywords:
- queue header
ms.assetid: 24fcf350-eb0e-48cf-9fef-978be1aeda1f
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
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: 2e3bdbd8bfe0b288d9f6dec5251ffeff2e3c5f81
ms.lasthandoff: 02/24/2017

---
# <a name="ltqueuegt"></a>&lt;queue&gt;
テンプレート クラスの priority_queue と queue、および複数のサポート テンプレートを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
#include <queue>  
  
```  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator!=](../standard-library/queue-operators.md#operator_neq)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクトと等しくないかどうかをテストします。|  
|[operator<](../standard-library/queue-operators.md#operator_lt_)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクトより小さいかどうかをテストします。|  
|[operator\<=](../standard-library/queue-operators.md#operator_lt__eq)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクト以下かどうかをテストします。|  
|[operator==](../standard-library/queue-operators.md#operator_eq_eq)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクトと等しいかどうかをテストします。|  
|[operator>](../standard-library/queue-operators.md#operator_gt_)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクトより大きいかどうかをテストします。|  
|[operator>=](../standard-library/queue-operators.md#operator_gt__eq)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクト以上かどうかをテストします。|  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[queue クラス](../standard-library/queue-class.md)|基になるコンテナー型の前後の要素へのアクセスを制限することにより、機能の制限を提供するテンプレート コンテナーのアダプター クラスです。|  
|[priority_queue クラス](../standard-library/priority-queue-class.md)|基になるコンテナー型の先頭にあって常に最大になる要素へのアクセスを制限することにより、機能の制限を提供するテンプレート コンテナーのアダプター クラスです。|  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)


