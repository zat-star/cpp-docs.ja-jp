---
title: "setjmp/longjmp の使用 | Microsoft Docs"
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
  - "longjmp"
  - "setjmp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ 例外処理, setjmp/longjmp 関数"
  - "longjmp 関数 (C++ のプログラム内)"
  - "setjmp 関数"
  - "setjmp 関数, C++ プログラム"
  - "SETJMP.H"
  - "SETJMPEX.H"
ms.assetid: 96be8816-f6f4-4567-9a9c-0c3c720e37c5
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# setjmp/longjmp の使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[setjmp](../c-runtime-library/reference/setjmp.md) と [longjmp](../c-runtime-library/reference/longjmp.md) を一緒に使用すると、非ローカルの `goto` を実行することができます。  これらは通常、標準呼び出し規約や復帰規約を使用せずに、前に呼び出されたルーチンのエラー処理または回復コードに実行の制御を渡すために使用されます。  
  
> [!CAUTION]
>  ただし、`setjmp` と `longjmp` は C\+\+ オブジェクトのセマンティクスをサポートせず、ローカル変数の最適化を妨げることによってパフォーマンスを低下させる可能性があるため、C\+\+ プログラムでは使用しないことをお勧めします。  代わりに、`try`\/`catch` 構造を使用することをお勧めします。  
  
 C\+\+ プログラムで `setjmp`\/`longjmp` を使用することにした場合は、SETJMP.H または SETJMPEX.H もインクルードして、関数と C\+\+ 例外処理との相互作用が正しく行われるようにします。  コンパイルで [\/EH](../build/reference/eh-exception-handling-model.md) を使用すると、スタック アンワインド中にローカル オブジェクトのデストラクターが呼び出されます。  コンパイルで **\/EHs** を使用し、関数の 1 つが [nothrow](../Topic/nothrow%20\(C++\).md) を使用する関数を呼び出して、`nothrow` を使用する関数が `longjmp` を呼び出すと、オプティマイザーによってはデストラクター アンワインドが実行されない場合があります。  
  
 移植性のあるコードで、`longjmp` を呼び出す非ローカルの `goto` が実行される場合、フレーム ベースのオブジェクトの適切な破棄が行われない可能性があります。  
  
## 参照  
 [C \(構造化\) と C\+\+ の混合例外](../Topic/Mixing%20C%20\(Structured\)%20and%20C++%20Exceptions.md)