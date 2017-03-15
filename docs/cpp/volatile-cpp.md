---
title: "volatile (C++) | Microsoft Docs"
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
  - "volatile_cpp"
  - "volatile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "割り込みハンドラーと volatile キーワード"
  - "オブジェクト [C++], volatile"
  - "volatile キーワード [C++]"
  - "volatile オブジェクト"
ms.assetid: 81db4a85-ed5a-4a2c-9a53-5d07a771d2de
caps.latest.revision: 43
caps.handback.revision: 43
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# volatile (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

オブジェクトをハードウェアがプログラム内で変更できることを宣言するために使用できる型修飾子です。  
  
## 構文  
  
```  
  
volatile declarator ;  
```  
  
## 解説  
 このキーワードをコンパイラが解釈する方法を変更するために、[\/volatile](../build/reference/volatile-volatile-keyword-interpretation.md) コンパイラ スイッチを使用できます。  
  
 Visual Studio は、ターゲット アーキテクチャに応じて、`volatile` キーワードの解釈を変えます。  ARM の場合、**\/volatile** コンパイラ オプションが指定されないと、コンパイラは **\/volatile:iso** が指定されたかのように動作します。  ARM 以外のアーキテクチャの場合は、**\/volatile** コンパイラ オプションが指定されないと、コンパイラは **\/volatile:ms** が指定されたかのように動作します。そのため、ARM 以外のアーキテクチャでは、複数のスレッド間で共有されるメモリを扱う場合、**\/volatile:iso** を指定し、明示的な同期プリミティブとコンパイラ組み込み関数を使用することを強くお勧めします。  
  
 `volatile` 修飾子を使用すると、割り込みハンドラーのような非同期プロセスによって使用されるメモリ位置へのアクセスを提供することができます。  
  
 [\_\_restrict](../cpp/extension-restrict.md) キーワードも持っている変数に対して `volatile` を使用すると、`volatile` が優先されます。  
  
 `struct` メンバーが `volatile` としてマークされている場合、`volatile` は構造体全体に反映されます。  構造体に、1 つの命令を使用して現在のアーキテクチャでコピーできる長さがない場合、`volatile` がその構造体で完全に失われることがあります。  
  
 次のいずれかの条件が当てはまる場合、`volatile` キーワードはフィールドに対して効果を持ちません。  
  
-   volatile フィールドの長さが、現在のアーキテクチャで 1 つの命令を使用してコピーできる最大サイズを超えている。  
  
-   入れ子になる可能性がある `struct` のメンバーである場合に、最も外側を囲んでいる `struct` の長さが、現在のアーキテクチャで 1 つの命令を使用してコピーできる最大サイズを超えている。  
  
 プロセッサはキャッシュ不可能なメモリ アクセスの順序を変更しませんが、キャッシュ不可能な変数は、コンパイラがメモリ アクセスの順序を変更しないことを保証するために、`volatile` としてマークする必要があります。  
  
 値がいつでも変更可能であるため、`volatile` として宣言されるオブジェクトは、特定の最適化では使用されません。  システムは、以前の命令で同じオブジェクトの値が要求されていても、常に volatile オブジェクトの現在の値を、要求されたときに読み取ります。  また、オブジェクトの値は、代入時にすぐに書き込まれます。  
  
## ISO 準拠 →  
 [C\# volatile](../Topic/volatile%20\(C%23%20Reference\).md) キーワードに慣れていたり、以前のバージョンの Visual C\+\+ `volatile` の動作に慣れていたりする場合は、C\+\+11 ISO 標準の `volatile` キーワードは異なっており、[\/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) コンパイラ オプションが指定された場合に Visual Studio でサポートされることに注意してください。 ARM では、このオプションが既定で指定されています。  C\+\+11 ISO 標準コードの `volatile` キーワードは、ハードウェア アクセスにのみ使用してください。スレッド間通信には使用しないでください。  スレッド間通信には、[C\+\+ 標準テンプレート ライブラリ](../standard-library/cpp-standard-library-reference.md)の [std::atomic\<T\>](../standard-library/atomic.md) などの機構を使用します。  
  
## END ISO 準拠  
  
## Microsoft 固有の仕様 →  
 **\/volatile:ms** コンパイラ オプションが使用される場合 \(既定では、ARM 以外のアーキテクチャがターゲットになる場合\)、コンパイラは volatile オブジェクトへの参照の順序と、その他のグローバル オブジェクトへの参照の順序を保持するために、追加のコードを生成します。  特に次の点に注意してください。  
  
-   volatile オブジェクトへの書き込み \(volatile 書き込み\) は、解放セマンティクスを持っています。つまり、命令シーケンスで volatile オブジェクトへの書き込み前に発生するグローバル オブジェクトまたは静的オブジェクトへの参照は、コンパイルされたバイナリでの volatile 書き込みの前に発生します。  
  
-   volatile オブジェクトの読み取り \(volatile 読み取り\) は、取得セマンティクスを持っています。つまり、命令シーケンスで volatile メモリの読み取り後に発生するグローバル オブジェクトまたは静的オブジェクトへの参照は、コンパイルされたバイナリでの volatile 読み取りの後に発生します。  
  
 これによって、マルチスレッド アプリケーションでのメモリのロックと解放に volatile オブジェクトを使用できるようになります。  
  
> [!NOTE]
>  **\/volatile:ms** コンパイラ オプションの使用によって提供される強化された保証に依存するコードは、移植不可能です。  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [const](../cpp/const-cpp.md)   
 [const ポインターと volatile ポインター](../Topic/const%20and%20volatile%20Pointers.md)