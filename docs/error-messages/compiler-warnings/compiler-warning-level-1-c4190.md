---
title: "コンパイラの警告 (レベル 1) C4190 | Microsoft Docs"
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
  - "C4190"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4190"
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4190
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier1' は C リンケージ指定ですが、C と互換性のないユーザー定義の型 'identifier2' を返しています。  
  
 関数または関数へのポインターで、戻り値の型がユーザー定義型 \(UDT: User\-Defined Type\) で、`extern` "C" リンケージがあります。ユーザー定義型は、クラス、構造体、列挙型、共用体、または [\_\_value](../../misc/value.md) 型です。  この指定が有効なのは、次の場合です。  
  
-   この関数の呼び出しがすべて C\+\+ から発生する場合。  
  
-   関数の定義が C\+\+ にある場合。  
  
## 使用例  
  
```  
// C4190.cpp  
// compile with: /W1 /LD  
struct X  
{  
   int i;  
   X ();  
   virtual ~X ();  
};  
  
extern "C" X func ();   // C4190  
```