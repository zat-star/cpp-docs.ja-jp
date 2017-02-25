---
title: "コンパイラの警告 (レベル 4) C4673 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4673"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4673"
ms.assetid: 95626ec6-f05b-43c7-8b9a-a60a6f98dd30
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 4) C4673
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' のスロー。次の型はキャッチ側では評価されません。  
  
 スローされるオブジェクトは、**catch** ブロックの中で処理できません。  この警告に続いて、処理できない型の一覧がエラー出力に表示されます。  各型にはそれぞれ対応する警告が付加されています。  詳細については、各型の警告を参照してください。  
  
 次の例では警告 C4673 が生成されます。  
  
```  
// C4673.cpp  
// compile with: /EHsc /W4  
class Base {  
private:  
   char * m_chr;  
public:  
   Base() {  
      m_chr = 0;  
   }  
  
   ~Base() {  
      if(m_chr)  
         delete m_chr;  
   }  
};  
  
class Derv : private Base {  
public:  
   Derv() {}  
   ~Derv() {}  
};  
  
int main() {  
   try {  
      Derv D1;  
      // delete previous line, uncomment the next line to resolve  
      // Base D1;  
      throw D1;   // C4673  
   }  
  
   catch(...) {}  
}  
```