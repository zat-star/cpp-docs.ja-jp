---
title: "&lt; キュー &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::<queue>"
  - "std.<queue>"
  - "<queue>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "queue ヘッダー"
ms.assetid: 24fcf350-eb0e-48cf-9fef-978be1aeda1f
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# &lt; キュー &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

テンプレート クラスの priority_queue と queue、および複数のサポート テンプレートを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
#include <queue>  
  
```  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator! =](../Topic/%3Cqueue%3E%20operators.md#operator_neq)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクトと等しくないかどうかをテストします。|  
|[演算子 <](../Topic/%3Cqueue%3E%20operators.md#operator_lt_)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクトより小さいかどうかをテストします。|  
|[operator \< =](../Topic/%3Cqueue%3E%20operators.md#operator_lt__eq)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクト以下かどうかをテストします。|  
|[演算子 = =](../Topic/%3Cqueue%3E%20operators.md#operator_eq_eq)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクトと等しいかどうかをテストします。|  
|[演算子 >](../Topic/%3Cqueue%3E%20operators.md#operator_gt_)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクトより大きいかどうかをテストします。|  
|[operator > =](../Topic/%3Cqueue%3E%20operators.md#operator_gt__eq)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクト以上かどうかをテストします。|  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[queue クラス](../standard-library/queue-class.md)|基になるコンテナー型の前後の要素へのアクセスを制限することにより、機能の制限を提供するテンプレート コンテナーのアダプター クラスです。|  
|[priority_queue クラス](../standard-library/priority-queue-class.md)|基になるコンテナー型の先頭にあって常に最大になる要素へのアクセスを制限することにより、機能の制限を提供するテンプレート コンテナーのアダプター クラスです。|  
  
## <a name="see-also"></a>参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)

