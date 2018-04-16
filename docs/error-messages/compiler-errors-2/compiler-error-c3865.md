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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cec5eabe6f4fa62648e9d3787d8ef2d2133f7736
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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