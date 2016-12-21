---
title: "コンパイラ エラー C3286 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3286"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3286"
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3286
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'specifier': 繰り返し変数は、ストレージ クラスの指定子を含むことはできません  
  
 詳細については、「[\(NOTINBUILD\) ストレージ クラス指定子](http://msdn.microsoft.com/ja-jp/10b3d22d-cb40-450b-994b-08cf9a211b6c)」を参照してください。  
  
 詳細については、「[for each、in](../../dotnet/for-each-in.md)」を参照してください。  
  
## 使用例  
 次の例では C3286 が生成されます。  
  
```  
// C3286.cpp // compile with: /clr int main() { array<int> ^p = { 1, 2, 3 }; for each (static int i in p) {}   // C3286 for each (int j in p) {}   // OK }  
```