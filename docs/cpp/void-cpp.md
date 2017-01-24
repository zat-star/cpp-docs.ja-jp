---
title: "void (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "void"
  - "void_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "関数 [C++], void"
  - "ポインター, void"
  - "void キーワード [C++]"
ms.assetid: d203edba-38e6-4056-8b89-011437351057
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# void (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

関数の戻り値の型として `void` キーワードを使用した場合は、関数が値を戻さないことを示します。  関数のパラメーター リストで void を使用した場合は、関数がパラメーターを受け取らないことを示します。  ポインターの宣言で void を使用した場合は、ポインターが "汎用" であることを示します。  
  
 ポインター型が **void \*** の場合は、**const** キーワードまたは `volatile` キーワードで宣言されていないすべての変数を指し示すことができます。  void ポインターは別の型にキャストしない限り、逆参照できません。  void ポインターは他の型のデータ ポインターに変換できます。  
  
 void ポインターは、関数を指すことはできますが、C\+\+ のクラス メンバーを指すことはできません。  
  
 void 型の変数を宣言することはできません。  
  
## 使用例  
  
```  
// void.cpp  
void vobject;   // C2182  
void *pv;   // okay  
int *pint; int i;  
int main() {  
   pv = &i;  
   // Cast optional in C required in C++  
   pint = (int *)pv;  
}   
```  
  
## 参照  
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [void 型へのポインター](../misc/pointers-to-type-void.md)   
 [基本型](../cpp/fundamental-types-cpp.md)