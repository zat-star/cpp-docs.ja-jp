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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 25df5237d2536f6f74226121cbeceba61a454390
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2585"></a>コンパイラ エラー C2585
'type' に明示的な変換があいまいです。  
  
 型変換は、複数の結果を生成できます。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  多重継承に基づく、クラスまたは構造体の型から変換します。 変換関数または演算子がスコープ解決演算子を使用する必要があります、型では、同じ基本クラスが 2 回以上継承している場合 (`::`) の変換で使用する継承されたクラスを指定します。  
  
2.  同じ変換を行う変換演算子と、コンス トラクターを定義しました。