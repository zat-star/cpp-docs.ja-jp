---
title: "コンパイラの警告 (レベル 1) C4628 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4628"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4628"
ms.assetid: 20fdc6f8-5f6a-40cc-aff8-c7ccf3d8ec26
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 1) C4628
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

digraphs は \-Ze でサポートされていません。文字のシーケンス 'digraph' は 'char' の代替トークンとして解釈されません。  
  
 digraph は、[\/Ze](../../build/reference/za-ze-disable-language-extensions.md) でサポートされていません。  この警告の後にはエラーが続きます。  
  
 既定では、この警告はオフに設定されています。  詳細については、「[Compiler Warnings That Are Off by Default](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。  
  
 次の例では警告 C4628 が生成されます。  
  
```  
// C4628.cpp  
// compile with: /WX  
#pragma warning(default : 4628)  
int main()  
<%   // C4628 <% digraph for {  
}  
```