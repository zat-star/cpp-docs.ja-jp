---
title: コンパイラ エラー C2828 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
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
ms.workload:
- cplusplus
ms.openlocfilehash: bc78f876056c09a27de3766812dbc22eefe1848d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2828"></a>コンパイラ エラー C2828
'operator 演算子' は、バイナリ形式でグローバルに上書きすることはできません。  
  
 演算子は、オブジェクトの外部でバイナリ形式を持つことはできません。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  オブジェクトにローカルのオーバー ロードされた演算子を加えます。  
  
2.  適切な単項演算子をオーバー ロードを選択します。