---
title: "コンパイラ エラー C2653 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2653"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2653"
  - "CDaoRecordset クラス, 追加 (レコードを)"
ms.assetid: 3f49e731-affd-43a0-a8d0-181db7650bc3
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2653
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 識別子がクラス名でも名前空間名でもありません。  
  
 構文には、クラス、構造体、共用体、または名前空間名が必要です。  
  
 次の例では警告 C2653 が生成されます。  
  
```  
// C2653.cpp  
// compile with: /c  
class yy {  
   void func1(int i);  
};  
  
void xx::func1(int m) {}   // C2653  
void yy::func1(int m) {}   // OK  
```  
  
 複合名前空間を定義しようとした場合も、C2653 が発生することがあります。複合名前空間は C\+\+ では使用できません。  
  
```  
// C2653b.cpp  
namespace a::b {int i;}   // C2653  
  
namespace a {  
   namespace b {  
      int i;  
   }  
}  
  
int main() {  
   a::b::i = 2;  
}  
```