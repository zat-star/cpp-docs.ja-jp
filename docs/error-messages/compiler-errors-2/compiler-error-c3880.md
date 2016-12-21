---
title: "コンパイラ エラー C3880 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3880"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3880"
ms.assetid: b0e05d1e-32d0-4034-9246-f37d23573ea9
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3880
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : リテラル データ メンバーになることはできません  
  
 [literal](../../windows/literal-cpp-component-extensions.md) 属性の型は、次のいずれかの型であるか、コンパイル時にそれらの型に変換できる必要があります。  
  
-   整数型  
  
-   string  
  
-   整数型または基になる型の列挙型 \(Enum\)  
  
 次の例では警告 C3880 が生成されます。  
  
```  
// C3880.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   literal System::Decimal staticConst1 = 10;   // C3880  
   literal int staticConst2 = 10;   // OK  
};  
```