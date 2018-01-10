---
title: "コンパイラの警告 (レベル 1) C4799 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4799
dev_langs: C++
helpviewer_keywords: C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9f41535c01d67e28baa2569ace2684865407a1d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4799"></a>コンパイラの警告 (レベル 1) C4799  
  
> 関数の最後にない EMM '*関数*'  
  
関数は、少なくとも 1 つの MMX 命令を持つ必要はありません、`EMMS`命令します。 マルチ メディアの命令を使用すると、`EMMS`命令または`_mm_empty`組み込みを使用することも MMX コードの最後に、マルチ メディア タグ単語をオフにします。  
  
返す前に EMMS 命令 ivec.h コードが正しく使用されないことを使用して実行すると、C4799 を表示可能性があります。 これは、これらのヘッダーの場合は false 警告です。 これら操作は、ivec.h で _SILENCE_IVEC_C4799 を定義することで無効に可能性があります。 ただし、これでも保持すること、コンパイラからこの型の正しい警告に注意してください。  
  
関連情報については、次を参照してください。 [Intel's MMX 命令セット](../../assembler/inline/intel-s-mmx-instruction-set.md)です。