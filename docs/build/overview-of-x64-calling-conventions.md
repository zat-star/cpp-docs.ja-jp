---
title: "x64 呼び出し規約の概要 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: a05db5eb-0844-4d9d-8b92-b1b2434be0ea
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# x64 呼び出し規約の概要
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

x86 から [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] への 2 つの重要な変更点は、64 ビット アドレッシング機能と 16 個の 64 ビット汎用レジスタのフラットなセットです。  拡張されたレジスタ セットの場合、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)] は [\_\_fastcall](../cpp/fastcall.md) 呼び出し規約および RISC ベースの例外処理モデルを使用します。  `__fastcall` モデルは最初の 4 つの引数のためのレジスタと、その他のパラメーターを渡すためのスタック フレームを使用します。  
  
 次のコンパイラ オプションを使用すると、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)] 対応アプリケーションを最適化できます。  
  
-   [\/favor \(アーキテクチャ固有の最適化\)](../build/reference/favor-optimize-for-architecture-specifics.md)  
  
## 呼び出し規約  
 [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] ABI \(Application Binary Interface\) は 4 レジスタ fast\-call 呼び出し規約であり、これらのレジスタのスタック バッキングを使用します。  関数の引数と引数のレジスタは厳密に 1 対 1 で対応します。  8 バイト以内に収まらない引数、または 1、2、4、8 バイト以外の引数は、参照により渡される必要があります。  1 つの引数が複数のレジスタにわたって展開されることはありません。  x87 レジスタ スタックは使用されません。  使用することは可能ですが、関数呼び出しでは揮発性であると考える必要があります。  すべての浮動小数点演算は、16 個の XMM レジスタを使用して行われます。  引数は、RCX、RDX、R8、および R9 レジスタで渡されます。  引数が float\/double 型の場合は、XMM0L、XMM1L、XMM2L、および XMM3L で渡されます。  16 バイトの引数は参照により渡されます。  パラメーターの引き渡しについては、「[パラメーターの引き渡し](../build/parameter-passing.md)」で詳しく説明します。  これらのレジスタに加えて、RAX、R10、R11、XMM4、および XMM5 は揮発性です。  他のすべてのレジスタは不揮発性です。  レジスタの使用については、「[レジスタの使用](../build/register-usage.md)」および「[呼び出し元または呼び出し先保存済みレジスタ](../build/caller-callee-saved-registers.md)」で詳しく説明します。  
  
 呼び出し元は、パラメーターに必要な領域を呼び出し先に割り当てる責任があり、呼び出し先がそれだけのパラメーターを持たない場合でも、常に 4 つのレジスタ パラメーターに対して十分な領域を割り当てる必要があります。  これは、C のプロトタイプ宣言されていない関数、および vararg C\/C\+\+ 関数のサポートを簡略化します。  vararg 関数またはプロトタイプ宣言されていない関数の場合、浮動小数点値は対応する汎用レジスタで重複される必要があります。  最初の 4 つを超える任意のパラメーターは、呼び出しの前に、最初の 4 つのバッキング ストアの上に保存されます。  vararg 関数の詳細については、「[vararg](../build/varargs.md)」を参照してください。  プロトタイプ宣言されていない関数の詳細については、「[プロトタイプ宣言されていない関数](../build/unprototyped-functions.md)」を参照してください。  
  
## \[配置\]  
 ほとんどの構造体はそれらの自然な形式に配置されます。  主な例外はスタック ポインターと malloc メモリまたは alloca メモリです。これらは、パフォーマンスを支援するために 16 バイトに配置されます。  16 バイトを超える配置は手動で行う必要がありますが、16 バイトは XMM 演算の共通の配置サイズであるため、ほとんどのコードはこれで十分だといえます。  構造体のレイアウトおよび配置の詳細については、「[型とストレージ](../build/types-and-storage.md)」を参照してください。  スタック レイアウトの詳細については、「[スタックの使用](../build/stack-usage.md)」を参照してください。  
  
## アンワインド可能性  
 リーフ関数 \(関数を呼び出したり、任意のスタック領域に自身を割り当てたりしない関数\) 以外のすべての関数には、不揮発性レジスタを回復するために、それらを正しくアンワインドする方法をオペレーティング システムに対して記述したデータで注釈を付ける必要があります。このデータは xdata または ehdata と呼ばれ、pdata から指されます。  Prolog と epilog は、xdata で正しく記述されるように大幅に制限されます。  スタック ポインターは、リーフ関数を除いて、epilog または prolog の一部でない任意のコード領域で 16 バイトに配置される必要があります。  prolog および epilog 関数の正しい構造の詳細については、「[プロローグとエピローグ](../build/prolog-and-epilog.md)」を参照してください。  例外処理および例外処理\/アンワインディング pdata および xdata の詳細については、「[例外処理 \(x64\)](../build/exception-handling-x64.md)」を参照してください。  
  
## 参照  
 [x64 ソフトウェア規約](../build/x64-software-conventions.md)