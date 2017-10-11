---
title: "致命的なエラー C1002 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1002
dev_langs:
- C++
helpviewer_keywords:
- C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cab0e1db2d84fb5ba84d773f28e70341faf10ac6
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1002"></a>致命的なエラー C1002
パス 2 の実行中に、ヒープ領域を使い果たしました。  
  
 コンパイラはおそらくシンボルまたは複雑な式が多すぎるとプログラムにより、2 番目のパスの中に動的メモリの領域不足になりました。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  ソース ファイルをいくつかの小さなファイルに分割します。  
  
2.  式を小さな部分に分割します。  
  
3.  その他のプログラムまたはメモリを消費するドライバーを削除します。
