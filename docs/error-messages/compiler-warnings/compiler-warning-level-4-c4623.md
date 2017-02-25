---
title: "コンパイラの警告 (レベル 4) C4623 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4623"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4623"
ms.assetid: e630d8d0-f6ea-469c-a74f-07b027587225
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラの警告 (レベル 4) C4623
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'`derived class`' : 基底クラスの既定のコンストラクターがアクセスできないか削除されているため、既定のコンストラクターは暗黙的に削除済みとして定義されました  
  
 コンストラクターは基底クラスでアクセスできないため、派生クラスでは生成されません。  スタックにこの型のオブジェクトを作成しようとすると、コンパイル エラーが発生します。  
  
 既定では、この警告はオフに設定されています。  詳細については、「[既定で無効になっているコンパイラ警告](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。  
  
## 使用例  
 次の例では C4623 警告が生成されます。  
  
```  
// C4623.cpp  
// compile with: /W4  
#pragma warning(default : 4623)  
class B {  
   B();  
};  
  
class C {  
public:  
   C();  
};  
  
class D : public B {};   // C4623 - to fix, make B's constructor public  
class E : public C {};   // OK - class C constructor is public  
  
int main() {  
   // D d;  will cause an error  
}  
```