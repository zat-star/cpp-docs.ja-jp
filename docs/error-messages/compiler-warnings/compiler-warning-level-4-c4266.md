---
title: "コンパイラの警告 (レベル 4) C4266 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4266"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4266"
ms.assetid: 90ec5f5b-3451-4c16-bb1b-c30a626bdaa0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 4) C4266
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' : 仮想メンバー関数用に基本クラス '型' から使用可能なオーバライドはありません。関数は隠されます。  
  
 派生クラスは、仮想関数のオーバーロードはすべてオーバーライドしませんでした。  
  
 既定では、この警告はオフに設定されています。詳細については、「[既定で無効になっているコンパイラ警告](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。  
  
 次の例では警告 C4266 が生成されます。  
  
```  
// C4266.cpp  
// compile with: /W4 /c  
#pragma warning (default : 4266)  
class Engine {  
public:  
   virtual void OnException(int&,int);  
   virtual void OnException(int&,int&,int);  
};  
  
class LocalBinding : private Engine {  
   virtual void OnException(int&,int);  
};   // C4266  
```  
  
 解決方法 :  
  
```  
// C4266b.cpp  
// compile with: /W4 /c  
#pragma warning (default : 4266)  
class Engine {  
public:  
   virtual void OnException(int&,int);  
   virtual void OnException(int&,int&,int);  
};  
  
class LocalBinding : private Engine {  
   virtual void OnException(int&,int);  
   virtual void OnException(int&, int&, int);  
};  
```