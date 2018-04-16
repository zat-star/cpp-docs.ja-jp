---
title: "コンパイラの警告 C4950 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4950
dev_langs:
- C++
helpviewer_keywords:
- C4950
ms.assetid: 50226a5c-c664-4d09-ac59-e9e874ca244f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0bad063bce3e99e64177476cea8470da0de81d3a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4950"></a>コンパイラの警告 C4950
'type_or_member': 廃止としてマークされています  
  
メンバーまたは型がで obsolete としてマークされた、<xref:System.ObsoleteAttribute>属性。  
  
C4950 は、常にエラーとして表示されます。 この警告をオフを使用して、[警告](../../preprocessor/warning.md)プラグマ ディレクティブまたは[/wd](../../build/reference/compiler-option-warning-level.md)コンパイラ オプション。  
  
## <a name="example"></a>例  
次の例では C4950 が生成されます。  
  
```cpp  
// C4950.cpp  
// compile with: /clr  
using namespace System;  
  
// Any reference to Func3 should generate an error with message  
[System::ObsoleteAttribute("Will be removed in next version", true)]  
Int32 Func3(Int32 a, Int32 b) {  
   return (a + b);  
}  
  
int main() {  
   Int32 MyInt3 = ::Func3(2, 2);   // C4950  
}  
```