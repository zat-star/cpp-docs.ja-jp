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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d299c6793e106ce516a81a9a81312ef0a09c25bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1002"></a>致命的なエラー C1002
パス 2 の実行中に、ヒープ領域を使い果たしました。  
  
 コンパイラはおそらくシンボルまたは複雑な式が多すぎるとプログラムにより、2 番目のパスの中に動的メモリの領域不足になりました。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  ソース ファイルをいくつかの小さなファイルに分割します。  
  
2.  式を小さな部分に分割します。  
  
3.  その他のプログラムまたはメモリを消費するドライバーを削除します。