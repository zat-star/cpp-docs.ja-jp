---
title: "コンパイラ エラー C2381 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2381
dev_langs:
- C++
helpviewer_keywords:
- C2381
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0442b94b1151dbee006a0d3ee71b1076d7afe7df
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2381"></a>コンパイラ エラー C2381
'function': 再定義されています。__declspec(noreturn) 異なります  
  
 関数が宣言されており、その定義が使用されますが、定義、 [noreturn](../../cpp/noreturn.md) `__declspec`修飾子です。 使用`noreturn`構成関数の再定義; 宣言と定義の使用に同意する必要があります。`noreturn`です。  
  
 次の例では、C2381 が生成されます。  
  
```  
// C2381.cpp  
// compile with: /c  
void f1();  
void __declspec(noreturn) f1() {}   // C2381  
void __declspec(noreturn) f2() {}   // OK  
```
