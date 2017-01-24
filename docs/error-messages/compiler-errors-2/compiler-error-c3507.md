---
title: "コンパイラ エラー C3507 | Microsoft Docs"
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
  - "C3507"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3507"
ms.assetid: 75f89767-f6f9-40f6-9820-81a49e09abdf
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3507
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ProgID に入力できる文字数は 39 以下です 'id'。また、'.' 以外の句読点を使用したり、数字を先頭に使用することはできません。  
  
 [progid](../Topic/progid.md) 属性に使用できる値には制限があります。  
  
 次の例では警告 C3507 が生成されます。  
  
```  
// C3507.cpp  
[module(name="x")];  
[  
coclass,  
progid("0123456789012345678901234567890123456789"),  
uuid("00000000-0000-0000-0000-000000000001") // C3507 expected  
]  
struct CMyStruct {  
};  
int main() {  
}  
```