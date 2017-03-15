---
title: "コンパイラの警告 (レベル 1) C4091 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4091"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4091"
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラの警告 (レベル 1) C4091
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'キーワード' : 変数が何も宣言されていないときは、'型' の左辺を無視します。  
  
 コンパイラは、ユーザーが変数を宣言しようとしたことを検出しましたが、変数を宣言できませんでした。  
  
## 使用例  
 ユーザー定義型の宣言の先頭で指定された `__declspec` 属性は、その型の変数に適用されます。  C4091 は、変数が宣言されていないことを示します。  次の例では C4091 エラーが生成されます。  
  
```  
// C4091.cpp  
// compile with: /W1 /c  
__declspec(dllimport) class X {}; // C4091  
  
// __declspec attribute applies to varX  
__declspec(dllimport) class X2 {} varX;  
  
// __declspec attribute after the class or struct keyword   
// applies to user defined type  
class __declspec(dllimport) X3 {};  
```  
  
## 使用例  
 識別子が typedef の場合は、変数名にすることもできません。  次の例では C4091 エラーが生成されます。  
  
```  
// C4091_b.cpp  
// compile with: /c /W1 /WX  
#define LIST 4  
typedef struct _LIST {} LIST;   // C4091  
```