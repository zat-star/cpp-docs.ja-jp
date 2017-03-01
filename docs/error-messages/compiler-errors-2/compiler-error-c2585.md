---
title: "コンパイラ エラー C2585 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2585
dev_langs:
- C++
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
caps.latest.revision: 6
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: ec9787e04d5c3539bf671a575a9487af94c3910d
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2585"></a>コンパイラ エラー C2585
'type' に明示的な変換はあいまいです。  
  
 型変換は、1 つの結果を生成できます。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  多重継承に基づく、クラスまたは構造体の型から変換します。 変換関数や演算子がスコープ解決演算子を使用する必要があります、型は複数回にわたって、同じ基本クラスを継承している場合 (`::`)、変換に使用する継承されたクラスを指定します。  
  
2.  同じ変換を行う変換演算子とコンス トラクターを定義されています。
