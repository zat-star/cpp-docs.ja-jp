---
title: "コンパイラ エラー C2885 | Microsoft Docs"
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
  - "C2885"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2885"
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2885
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class::identifier' : 非クラス スコープでは有効な using 宣言ではありません  
  
 [using](../../cpp/using-declaration.md) 宣言の使用方法が間違っています。  
  
## 使用例  
 このエラーは、Visual C\+\+ 2005 で行ったコンパイラ準拠作業の結果として生成されることがあります。`using` 宣言は、入れ子にされた型に対して使用できなくなりました。入れ子にされた型に対して作成する各参照を明示的に修飾し、その型を名前空間に入れるか、typedef を作成する必要があります。  
  
 次の例では C2885 エラーが生成されます。  
  
```  
// C2885.cpp  
namespace MyNamespace {  
   class X1 {};  
}  
  
struct MyStruct {  
   struct X1 {  
      int i;  
   };  
};  
  
int main () {  
   using MyStruct::X1;   // C2885  
  
   // OK  
   using MyNamespace::X1;  
   X1 myX1;  
  
   MyStruct::X1 X12;  
  
   typedef MyStruct::X1 abc;  
   abc X13;  
   X13.i = 9;  
}  
```  
  
## 使用例  
 クラス メンバーで `using` キーワードを使用する場合は、そのメンバーを別のクラス \(派生クラス\) の内部で定義する必要があります。  
  
 次の例では C2885 エラーが生成されます。  
  
```  
// C2885_b.cpp  
// compile with: /c  
class A {  
public:  
   int i;  
};  
  
void z() {  
   using A::i;   // C2885 not in a class  
}  
  
class B : public A {  
public:  
   using A::i;  
};  
```