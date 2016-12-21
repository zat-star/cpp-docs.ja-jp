---
title: "コンパイラの警告 (レベル 1) C4436 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
ms.assetid: 2b54a1fc-c9c6-4cc9-90be-faa44fc715d5
caps.latest.revision: 2
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4436
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンストラクターやデストラクター" class2」への仮想基本クラス「class1 "から dynamic\_cast が \/vd2 で部分的にコンパイルされたオブジェクトまたは定義します。\#pragma vtordisp \(2\) 有効に" class2」が失敗する  
  
 コンパイラは、次の特性を持つ `dynamic_cast` 操作が発生しました。  
  
-   キャストは、基本クラスのポインターから派生クラスのポインターです。  
  
-   派生クラスは、基本クラスを継承します。  
  
-   派生クラスは、仮想基本クラスの `vtordisp` フィールドがありません。  
  
-   キャストは派生クラスのコンストラクターまたはデストラクター、さらに派生クラスから継承するクラスにあります。  
  
 警告は部分的されたオブジェクトで実行されている場合 `dynamic_cast` が正しく機能しない可能性があることを示します。これは、派生のコンストラクターとデストラクターが、さらに派生オブジェクトのサブオブジェクトを使用した場合に発生します。警告で指定した派生クラスはそれ以上の派生である、警告は無視できます。  
  
## 使用例  
 次の例では C4436 を生成し、`vtordisp` されないフィールドから発生したコード生成に関する問題を示します。  
  
```cpp  
// C4436.cpp  
// To see the warning and runtime assert, compile with: /W1  
// To eliminate the warning and assert, compile with: /W1 /vd2  
//       or compile with: /W1 /DFIX  
#include <cassert>  
  
struct A  
{  
public:  
    virtual ~A() {}  
};  
  
#if defined(FIX)  
#pragma vtordisp(push, 2)  
#endif  
struct B : virtual A  
{  
    B()  
    {  
        A* a = static_cast<A*>(this);  
        B* b = dynamic_cast<B*>(a);     // C4436  
        assert(this == b);              // assert unless compiled with /vd2  
    }  
};  
#if defined(FIX)  
#pragma vtordisp(pop)  
#endif  
  
struct C : B  
{  
    int i;  
};  
  
int main()  
{  
    C c;  
}  
```  
  
## 参照  
 [dynamic\_cast 演算子](../../cpp/dynamic-cast-operator.md)   
 [vtordisp](../Topic/vtordisp.md)   
 [コンパイラの警告 \(レベル 4\) C4437](../../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md)