---
title: "致命的なエラー C1197 | Microsoft Docs"
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
  - "C1197"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1197"
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 致命的なエラー C1197
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'mscorlib.dll\_1' を参照できません。プログラムは 'mscorlib.dll\_2' を既に参照しました  
  
 コンパイラは共通言語ランタイムのバージョンと一致しますが、以前のバージョンの共通言語ランタイム ファイルを参照しようとしました。  
  
 このエラーを解決するには、コンパイルで使用するバージョンの Visual C\+\+ に付属している共通言語ランタイムのバージョンのファイルだけを参照します。  
  
## 使用例  
 次の例では警告 C1197 が生成されます。  
  
```  
// C1197.cpp  
// compile with: /clr /c  
// processor: x86  
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197  
// try the following line instead  
// #using "mscorlib.dll"  
```