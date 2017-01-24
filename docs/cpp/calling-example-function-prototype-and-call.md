---
title: "呼び出しの例: 関数プロトタイプと呼び出し | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "呼び出し規約, 例 [C++]"
  - "例 [C++], 呼び出し規約"
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 呼び出しの例: 関数プロトタイプと呼び出し
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 次の例では、さまざまな呼び出し規約を使用して関数呼び出しを行った結果を示しています。  
  
 この例は、次の関数スケルトンに基づいています。  `calltype` は適切な呼び出し規約に置き換えます。  
  
```  
void    calltype MyFunc( char c, short s, int i, double f );  
.  
.  
.  
void    MyFunc( char c, short s, int i, double f )  
    {  
    .  
    .  
    .  
    }  
.  
.  
.  
MyFunc ('x', 12, 8192, 2.7183);  
```  
  
 詳細については、「[呼び出し結果の例](../Topic/Results%20of%20Calling%20Example.md)」を参照してください。  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [呼び出し規約](../Topic/Calling%20Conventions.md)