---
title: "コンパイラ エラー C3865 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3865
dev_langs:
- C++
helpviewer_keywords:
- C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: af0873d70fcb4f947e838afba130279edf705ced
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3865"></a>コンパイラ エラー C3865
'calling_convention': ネイティブ メンバー関数でのみ使用できます  
  
 グローバル関数となった関数またはマネージ メンバー関数の呼び出し規約が使用されました。 呼び出し規約は、ネイティブ (マネージ) メンバー関数でのみ使用できます。  
  
 詳細については、次を参照してください。[呼び出し規約](../../cpp/calling-conventions.md)です。  
  
 次の例では、C3865 が生成されます。  
  
```  
// C3865.cpp  
// compile with: /clr  
// processor: x86  
void __thiscall Func(){}   // C3865  
  
// OK  
struct MyType {  
   void __thiscall Func(){}  
};  
```
