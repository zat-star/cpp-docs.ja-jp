---
title: "コンパイラ エラー C2585 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cb0720c7fa9cde9a735c4353bb6bf1d8714ff0fd
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2585"></a>コンパイラ エラー C2585
'type' に明示的な変換があいまいです。  
  
 型変換は、複数の結果を生成できます。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  多重継承に基づく、クラスまたは構造体の型から変換します。 変換関数または演算子がスコープ解決演算子を使用する必要があります、型では、同じ基本クラスが 2 回以上継承している場合 (`::`) の変換で使用する継承されたクラスを指定します。  
  
2.  同じ変換を行う変換演算子と、コンス トラクターを定義しました。
