---
title: "/Zc:trigraphs (トライグラフの置換) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Zc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc コンパイラ オプション (C++)"
  - "準拠コンパイラ オプション"
  - "Zc コンパイラ オプション (C++)"
  - "-Zc コンパイラ オプション (C++)"
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /Zc:trigraphs (トライグラフの置換)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/Zc:trigraphs** が指定されている場合、コンパイラは、トライグラフ文字シーケンスを対応する区切り文字で置き換えます。  トライグラフの置換を無効にするには、**\/Zc:trigraphs\-** を指定します。  既定では、**\/Zc:trigraphs** は無効になっています。  
  
## 構文  
  
```  
/Zc:trigraphs[-]  
```  
  
## 解説  
 トライグラフは、2 つの連続する疑問符 \("??"\) と、その後に続く一意の 3 番目の文字で構成されます。  たとえば、コンパイラは "??\=" というトライグラフを '\#' 文字で置き換えます。  トライグラフは、C ソース ファイルで、一部の区切り文字に対する適切なグラフィック表示がない文字セットを使用する場合に使われます。  
  
 C\/C\+\+ のトライグラフの一覧とトライグラフの使用方法の例については、「[トライグラフ](../Topic/Trigraphs.md)」を参照してください。  
  
## 参照  
 [\/Zc \(準拠\)](../../build/reference/zc-conformance.md)   
 [トライグラフ](../Topic/Trigraphs.md)