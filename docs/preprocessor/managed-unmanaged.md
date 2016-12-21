---
title: "マネージ、アンマネージ | Microsoft Docs"
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
  - "vc-pragma.unmanaged"
  - "managed_CPP"
  - "unmanaged_CPP"
  - "vc-pragma.managed"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "managed プラグマ"
  - "プラグマ, マネージ"
  - "プラグマ, アンマネージ"
  - "unmanaged プラグマ"
ms.assetid: f072ddcc-e1ec-408a-8ce1-326ddb60e4a4
caps.latest.revision: 15
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# マネージ、アンマネージ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

関数をマネージまたはアンマネージとしてコンパイルするために関数レベルの制御を有効にします。  
  
## 構文  
  
```  
  
        #pragma managed  
#pragma unmanaged  
#pragma managed([push,] on | off)  
#pragma managed(pop)  
```  
  
## 解説  
 [\/clr](../build/reference/clr-common-language-runtime-compilation.md) コンパイラ オプションは、関数をマネージまたはアンマネージとしてコンパイルするためのモジュール レベルの制御を提供します。  
  
 アンマネージ関数は、ネイティブ プラットフォーム用にコンパイルされ、プログラムのその部分の実行は、共通言語ランタイムによってネイティブ プラットフォームに渡されます。  
  
 関数は、**\/clr** が使用されると、既定でマネージとしてコンパイルされます。  
  
 これらのプラグマを適用するときは次のようにします。  
  
-   関数の前にあり関数本体内にはないプラグマを追加します。  
  
-   `#include` ステートメントの後にプラグマを追加します。  `#include` ステートメントの前でこれらのプラグマを使用しないでください。  
  
 コンパイラは、コンパイルで `managed` が使用されない場合、`unmanaged` および **\/clr** プラグマを無視します。  
  
 テンプレート関数がインスタンス化されるとき、テンプレートの定義時のプラグマの状態により、マネージかアンマネージかが決まります。  
  
 詳細については、「[混在アセンブリの初期化](../Topic/Initialization%20of%20Mixed%20Assemblies.md)」を参照してください。  
  
## 使用例  
  
```  
// pragma_directives_managed_unmanaged.cpp  
// compile with: /clr  
#include <stdio.h>  
  
// func1 is managed  
void func1() {  
   System::Console::WriteLine("In managed function.");  
}  
  
// #pragma unmanaged  
// push managed state on to stack and set unmanaged state  
#pragma managed(push, off)  
  
// func2 is unmanaged  
void func2() {  
   printf("In unmanaged function.\n");  
}  
  
// #pragma managed  
#pragma managed(pop)  
  
// main is managed  
int main() {  
   func1();  
   func2();  
}  
```  
  
  **マネージ関数の場合。  アンマネージ関数の場合**    
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)