---
title: "コンパイラ エラー C2364 | Microsoft Docs"
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
  - "C2364"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2364"
ms.assetid: 4f550571-94b5-42ca-84cb-663fecbead44
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2364
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': カスタムの属性として不適切な型です。  
  
 カスタム属性の名前付き引数は、コンパイル時定数に限定されます。  たとえば、整数型 \(int、char など\)、System::Type^、および System::Object^ です。  
  
## 使用例  
 次の例では C2364 エラーが生成されます。  
  
```  
// c2364.cpp  
// compile with: /clr /c  
using namespace System;  
  
[attribute(AttributeTargets::All)]  
public ref struct ABC {  
public:  
   // Delete the following line to resolve.  
   ABC( Enum^ ) {}   // C2364  
   ABC( int ) {}   // OK  
};  
```