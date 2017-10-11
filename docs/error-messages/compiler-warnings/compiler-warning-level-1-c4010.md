---
title: "コンパイラの警告 (レベル 1) C4010 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4010
dev_langs:
- C++
helpviewer_keywords:
- C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b6a0c84d5138cf2ae8a7a6279d9dc0fde9fe9512
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-level-1-c4010"></a>コンパイラの警告 (レベル 1) C4010
単一行コメントには、行連結文字が含まれています。  
  
 導入された、単一行のコメント//、円記号が含まれています (\\) 行連結文字として機能します。 コンパイラでは、継続タスクを次の行を考慮し、コメントとして扱われます。  
  
 一部の構文向けエディターは、コメントとして連結文字の次の行を示していません。 構文の色分けでこの警告が発生した行を無視します。  
  
 次の例では、C4010 が生成されます。  
  
```  
// C4010.cpp  
// compile with: /WX  
int main() {  
   // the next line is also a comment because of the backslash \  
   int a = 3; // C4010  
   a++;  
}  
```
