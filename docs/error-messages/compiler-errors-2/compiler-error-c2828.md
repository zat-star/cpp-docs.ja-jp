---
title: "コンパイラ エラー C2828 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2828
dev_langs:
- C++
helpviewer_keywords:
- C2828
ms.assetid: d8df6ed4-5954-46c2-b59b-52881d4e923d
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8a461ae14edfbdffa9bd30068a7e935fb44817a6
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2828"></a>コンパイラ エラー C2828
'operator 演算子' は、バイナリ形式でグローバルに上書きすることはできません。  
  
 演算子は、オブジェクトの外部でバイナリ形式を持つことはできません。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  オブジェクトにローカルのオーバー ロードされた演算子を加えます。  
  
2.  適切な単項演算子をオーバー ロードを選択します。
