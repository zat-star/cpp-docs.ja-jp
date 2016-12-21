---
title: "コンパイラ エラー C3156 | Microsoft Docs"
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
  - "C3156"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3156"
ms.assetid: 1876da78-b94e-4af7-9795-28f72b209b3e
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3156
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : マネージ型または WinRT 型のローカル定義を持つことができません  
  
 関数に、マネージ型または WinRT 型のクラス、構造体、インターフェイスの定義 \(宣言\) を含めることはできません。  
  
## 使用例  
 次の例では C3156 が生成されます。  
  
```  
// C3156.cpp  
// compile with: /clr /c  
void f() {  
   ref class X {};   // C3156  
   ref class Y;   // C3156  
}  
```  
  
## 使用例  
 次の例では C3156 が生成されます。  
  
```  
// C3156_b.cpp  
// compile with: /clr:oldSyntax /c  
void f() {  
   __gc class X {};   // C3156  
   __gc class Y;   // C3156  
}  
```