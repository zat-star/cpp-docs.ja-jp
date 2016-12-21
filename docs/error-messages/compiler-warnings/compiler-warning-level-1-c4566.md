---
title: "コンパイラの警告 (レベル 1) C4566 | Microsoft Docs"
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
  - "C4566"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4566"
ms.assetid: 65f40730-e86f-447c-b37b-16caadcfe311
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4566
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ユニバーサル文字名 'char' によって表示されている文字は、現在のコード ページ \('ページ'\) で表示できません  
  
 一部の Unicode 文字は、現在の ANSI コード ページに表示できません。  
  
 半角文字 \(1 バイトの文字\) はマルチバイトの文字に変換できますが、全角文字 \(2 バイトの文字\) は変換できません。  
  
 次の例では警告 C4566 が生成されます。  
  
```  
// C4566.cpp  
// compile with: /W1  
int main() {  
   char c1 = '\u03a0';   // C4566  
   char c2 = '\u0642';   // C4566  
  
   wchar_t c3 = L'\u03a0';   // OK  
   wchar_t c4 = L'\u0642';   // OK  
}  
```