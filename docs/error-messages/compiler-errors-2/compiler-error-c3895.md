---
title: "コンパイラ エラー C3895 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3895"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3895"
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C3895
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : '型' データ メンバーを 'volatile' にすることはできません  
  
 [literal](../../windows/literal-cpp-component-extensions.md) や [initonly](../../dotnet/initonly-cpp-cli.md) などの特定の種類のデータ メンバーは [volatile](../../cpp/volatile-cpp.md) にできません。  
  
 次の例では警告 C3895 が生成されます。  
  
```  
// C3895.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly  
   volatile int data_var2;   // C3895  
};  
```