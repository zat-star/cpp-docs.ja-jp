---
title: "コンパイラ エラー C2628 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2628"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2628"
ms.assetid: 19a25e77-d5be-4107-88d5-0745b6281f98
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2628
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type2' の後に 'type1' を記述するのは正しくありません \(';' で区切られていない可能性があります\)。  
  
 セミコロンを付け忘れている可能性があります。  
  
 次の例では警告 C2628 が生成されます。  
  
```  
// C2628.cpp  
class CMyClass {}  
int main(){}   // C2628 error  
```  
  
 解決方法 :  
  
```  
// C2628b.cpp  
class CMyClass {};  
int main(){}  
```