---
title: "コンパイラの警告 (レベル 4) C4565 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4565
dev_langs:
- C++
helpviewer_keywords:
- C4565
ms.assetid: a71f1341-a4a1-4060-ad1e-9322531883ed
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b89da26312c68bc76d23fc829a14f17db3d601b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4565"></a>コンパイラの警告 (レベル 4) C4565
'function': 再定義されています。シンボルは以前 __declspec(modifier) で宣言されました  
  
 2 番目の定義または宣言の最初の定義または宣言とは異なり、ありませんでしたシンボルが再定義または再宣言され、`__declspec`修飾子 (***修飾子***)。 これは、情報提供の警告です。 この警告を解決するには、いずれかの定義を削除します。  
  
 次の例では、C4565 が生成されます。  
  
```  
// C4565.cpp  
// compile with: /W4 /LD  
__declspec(noalias) void f();  
void f();   // C4565  
```