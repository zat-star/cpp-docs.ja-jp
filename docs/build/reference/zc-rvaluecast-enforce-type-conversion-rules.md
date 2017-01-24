---
title: "/Zc:rvalueCast (型変換規則の適用) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "rvaluecast"
  - "/Zc:rvalueCast"
  - "VC.Project.VCCLCompilerTool.EnforceTypeConversionRules"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc コンパイラ オプション (C++)"
  - "適用 (型変換規則を)"
  - "rvaluecast"
  - "Zc コンパイラ オプション (C++)"
  - "-Zc コンパイラ オプション (C++)"
ms.assetid: 7825277d-e565-4c48-b0fb-76ac0b0c6e38
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:rvalueCast (型変換規則の適用)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/Zc:rvalueCast** オプションを指定した場合、コンパイラは C\+\+11 標準に従いキャスト操作の結果として右辺値参照型を正しく認識します。  このオプションを指定しない場合、コンパイラの動作は Visual Studio 2012 での動作と同じです。  既定では、**\/Zc:rvalueCast** は無効になっています。  標準に準拠し、キャスト使用時のエラーを回避するために、**\/Zc:rvalueCast** の使用をお勧めします。  
  
## 構文  
  
```  
/Zc:rvalueCast[-]  
```  
  
## 解説  
 **\/Zc:rvalueCast** が指定されると、コンパイラは C\+\+11 標準のセクション 5.4 に従って、非参照型になるキャスト式と、非関数型への右辺値参照になるキャスト式のみを右辺値参照型として扱います。  **\/Zc:rvalueCast\-** が指定されている場合、または既定では、コンパイラは非準拠となり、右辺値参照になるすべてのキャスト式を右辺値として扱います。  
  
 **\/Zc:rvalueCast** は、右辺値参照型を受け取る関数に引数としてキャスト式を渡す場合に使用します。  コンパイラが誤ってキャスト式の型を決定すると、既定の動作ではコンパイラ エラー [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) が発生します。  この例では、\/Zc:rvalueCast を指定しない場合に、正しいコードでコンパイラ エラーが表示されます。  
  
```cpp  
// Test of /Zc:rvalueCast  
// compile by using:  
// cl /c /Zc:rvalueCast- make_thing.cpp  
// cl /c /Zc:rvalueCast make_thing.cpp  
  
#include <utility>  
  
template <typename T>   
struct Thing {  
   // Construct a Thing by using two rvalue reference parameters  
   Thing(T&& t1, T&& t2)  
      : thing1(t1), thing2(t2) {}  
  
   T& thing1;  
   T& thing2;  
};  
  
// Create a Thing, using move semantics if possible  
template <typename T>  
Thing<T> make_thing(T&& t1, T&& t2)  
{  
   return (Thing<T>(std::forward<T>(t1), std::forward<T>(t2)));  
}  
  
struct Test1 {  
   long a;  
   long b;  
  
   Thing<long> test() {   
      // Use identity casts to create rvalues as arguments  
      return make_thing(static_cast<long>(a), static_cast<long>(b));   
   }  
};  
  
```  
  
 コンパイラの既定動作では、場合によっては C2102 エラーが報告されないことがあります。  この例で、**\/Zc:rvalueCast** を指定しない場合、ID のキャストによって作成された右辺値のアドレスを受け取ることができなくても、コンパイラはエラーを報告しません。  
  
```cpp  
int main() {  
   int a = 1;  
   int *p = &a;   // Okay, take address of lvalue   
                  // Identity cast creates rvalue from lvalue;    
   p = &(int)a;   // problem: should cause C2102: '&' requires l-value  
}  
```  
  
 Visual C\+\+ の準拠に関する問題の詳細については、「[非標準動作](../Topic/Nonstandard%20Behavior.md)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーを選択します。  
  
3.  **\[コマンド ライン\]** プロパティ ページを選択します。  
  
4.  **\/Zc:rvalueCast** が含まれるように **"追加オプション"** プロパティを変更し、**\[OK\]** をクリックします。  
  
## 参照  
 [\/Zc \(準拠\)](../../build/reference/zc-conformance.md)