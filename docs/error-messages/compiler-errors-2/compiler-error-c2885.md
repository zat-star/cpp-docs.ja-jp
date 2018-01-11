---
title: "コンパイラ エラー C2885 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2885
dev_langs: C++
helpviewer_keywords: C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 98f3501cc029094d7f00e941026c0f7d1ed7d80b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2885"></a>コンパイラ エラー C2885
':identifier': いない有効な using 宣言非クラス スコープで  
  
 使用する、[を使用して](../../cpp/using-declaration.md)宣言が正しくないです。  
  
## <a name="example"></a>例  
 このエラーは、Visual C 2005 で行ったコンパイラ準拠作業の結果として生成されることができます: これが有効ではなく、`using`入れ子になった型宣言を入れ子にされた型、名前に、型を配置する各参照を明示的に修飾する必要がありますスペース、または、typedef を作成します。  
  
 次の例では、C2885 を生成します。  
  
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
  
## <a name="example"></a>例  
 使用する場合、`using`クラスのメンバーでは、C++ のキーワードでは、そのメンバーを別のクラス (派生クラス) の内部を定義する必要があります。  
  
 次の例では、C2885 を生成します。  
  
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