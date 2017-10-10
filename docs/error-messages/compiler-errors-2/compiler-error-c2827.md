---
title: "コンパイラ エラー C2827 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2827
dev_langs:
- C++
helpviewer_keywords:
- C2827
ms.assetid: cb3e5814-0c92-40e4-b620-98578ae3003a
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e061c619ca936afaefe392fb808a22c1a19a27ba
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2827"></a>コンパイラ エラー C2827
単項形式にグローバルに 'operator 演算子' をオーバーライドすることはできません。  
  
 演算子は、オブジェクトの外側で単項形式を持つことはできません。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  オブジェクトにローカルのオーバー ロードされた演算子を加えます。  
  
2.  適切な単項演算子をオーバー ロードを選択します。
