---
title: "コンパイラ エラー C3747 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3747"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3747"
ms.assetid: a9a4be67-5d9c-4dcc-9ae9-baae46cbecde
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C3747
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

既定の '型' パラメーターが見つかりません : パラメーター 'param'  
  
 パラメーター リストでは、既定値を持つジェネリック パラメーターまたはテンプレート パラメーターに続けて既定値を持たないパラメーターを指定できません。  
  
 次の例では警告 C3747 が生成されます。  
  
```  
// C3747.cpp  
template <class T1 = int, class T2>   // C3747  
struct MyStruct {};  
```  
  
 解決方法 :  
  
```  
// C3747b.cpp  
// compile with: /c  
template <class T1, class T2 = int>  
struct MyStruct {};  
```