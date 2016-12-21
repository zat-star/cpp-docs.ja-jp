---
title: "コンパイラの警告 (レベル 4) C4238 | Microsoft Docs"
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
  - "C4238"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4238"
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4238
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

非標準の拡張機能が使用されています : 右辺値のクラスが左辺値に使用されます。  
  
 以前のバージョンの Visual C\+\+ との互換性を維持するために、Microsoft 拡張機能 \(**\/Ze**\) では、クラス型をそのアドレスを暗黙または明示的にとるコンテキストで右辺値として使用できます。  この使用方法は、次に示すコードのように、危険な場合があります。  
  
## 使用例  
  
```  
// C4238.cpp  
// compile with: /W4 /c  
struct C {  
   C() {}  
};  
  
C * pC = &C();   // C4238  
```  
  
 この使用方法は、ANSI 互換オプション \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) ではエラーとなります。