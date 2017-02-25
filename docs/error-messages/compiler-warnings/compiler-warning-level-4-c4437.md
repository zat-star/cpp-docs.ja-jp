---
title: "コンパイラの警告 (レベル 4) C4437 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
ms.assetid: dc07e350-20eb-474c-a7ad-f841ae7ec339
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# コンパイラの警告 (レベル 4) C4437
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

「class2」への仮想基本クラス「class1 "から dynamic\_cast が \/vd2 を指定してコンパイルするか、または定義します。\#pragma vtordisp \(2\) 有効に" class2」である場合は失敗する  
  
 既定では、この警告はオフに設定されています。  詳細については、「[既定で無効になっているコンパイラ警告](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。  
  
 コンパイラは、次の特性を持つ `dynamic_cast` 操作が発生しました。  
  
-   キャストは、基本クラスのポインターから派生クラスのポインターです。  
  
-   派生クラスは、基本クラスを継承します。  
  
-   派生クラスは、仮想基本クラスの `vtordisp` フィールドがありません。  
  
-   キャストは派生クラスのコンストラクターまたはデストラクター、さらに派生クラスから継承するクラスは \(それ以外の場合は、コンパイラの警告が発行されます C4436\)。  
  
 警告は部分的されたオブジェクトで実行されている場合 `dynamic_cast` が正しく機能しない可能性があることを示します。この状況は、外側の関数が警告に指定された派生クラスを継承するクラスのコンストラクターまたはデストラクターから呼び出されたときに発生します。警告で指定した派生クラスのオブジェクトの構築または破棄時にはそれ以上の派生、または外側の関数を呼び出す場合、警告は無視できます。  
  
## 使用例  
 次の例では C4437 を生成し、`vtordisp` されないフィールドから発生したコード生成に関する問題を示します。  
  
```cpp  
// C4437.cpp  
// To see the warning and runtime assert, compile with: /W4  
// To eliminate the warning and assert, compile with: /W4 /vd2  
//       or compile with: /W4 /DFIX  
#pragma warning(default : 4437)  
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
        func();  
    }  
  
    void func()  
    {  
        A* a = static_cast<A*>(this);  
        B* b = dynamic_cast<B*>(a);     // C4437  
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
 [コンパイラの警告 \(レベル 1\) C4436](../../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)