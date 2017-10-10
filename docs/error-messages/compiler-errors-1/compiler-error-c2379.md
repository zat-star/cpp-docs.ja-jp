---
title: "コンパイラ エラー C2379 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2379
dev_langs:
- C++
helpviewer_keywords:
- C2379
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 69be5132451269f7eba9c2e9186a9c25d4629ae7
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2379"></a>コンパイラ エラー C2379
正式なパラメーター数が昇格するときに別の種類  
  
 指定されたパラメーターの型は互換性のある、既定値のプロモーション、前の宣言で型を使用します。 これは ANSI C ではエラー ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) および Microsoft の拡張機能と警告 (**/Ze**)。  
  
 次の例では、C2379 が生成されます。  
  
```  
// C2379.c  
// compile with: /Za  
void func();  
void func(char);   // C2379, char promotes to int  
```
