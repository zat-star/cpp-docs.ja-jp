---
title: "コンパイラ エラー C2653 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2653
dev_langs:
- C++
helpviewer_keywords:
- C2653
ms.assetid: 3f49e731-affd-43a0-a8d0-181db7650bc3
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cc7990614283a20e9d07f52187258dbccad7c075
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2653"></a>コンパイラ エラー C2653
'identifier': クラスまたは名前空間名ではありません  
  
構文は、クラス、構造体、共用体、または名前空間の名前が必要です。  
  
次の例では、C2653 が生成されます。  
  
```cpp  
// C2653.cpp  
// compile with: /c  
class yy {  
   void func1(int i);  
};  
  
void xx::func1(int m) {}   // C2653  
void yy::func1(int m) {}   // OK  
```  
  
C2653 ことも可能です定義しようとする場合、*複合名前空間*、Visual Studio 2015 Update 3 より前の Visual C のバージョンを使用するときに、1 つまたは複数のスコープの入れ子になった名前空間名を含む名前空間。 複合の名前空間の定義が、c++ 17 の前に C++ では許可されていません。 Visual C++ 2015 Update 3 以降をコンパイラは複合名前空間の定義がサポートするときに、 [/std:c + + 最新](../../build/reference/std-specify-language-standard-version.md)コンパイラ オプションを指定します。  
```cpp  
// C2653b.cpp  
namespace a::b {int i;}   // C2653 prior to Visual C++ 2015 Update 3,  
                          // C2429 thereafter. Use /std:c++latest to fix.
namespace a {  
   namespace b {  
      int i;  
   }  
}  
  
int main() {  
   a::b::i = 2;  
}  
```  
