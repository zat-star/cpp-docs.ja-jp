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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: eb0c1bf407d1478451c246cf615d031ef6c45bf9
ms.openlocfilehash: 2203cf8a09dbb05f6145ed238ab9fc03e458aaa5
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2653"></a>コンパイラ エラー C2653
'identifier': クラスまたは名前空間名ではありません  
  
構文は、クラス、構造体、共用体、または名前空間の名前が必要です。  
  
次の例では、c2653 エラーが生成されます。  
  
```cpp  
// C2653.cpp  
// compile with: /c  
class yy {  
   void func1(int i);  
};  
  
void xx::func1(int m) {}   // C2653  
void yy::func1(int m) {}   // OK  
```  
  
C2653 を定義しようとする場合も、*複合名前空間*、Visual Studio 2015 の更新プログラム 3 より前の Visual C のバージョンを使用する場合に、1 つ以上のスコープにネストされた名前空間名を含む名前空間。 C++&17; する前に、定義は C++ では許可されませんが名前空間を合成します。 Visual C++ 2015 更新プログラム 3 以降、コンパイラは複合名前空間の定義をサポートと、 [/std:c では最新](../../build/reference/std-specify-language-standard-version.md)コンパイラ オプションを指定します。  
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
