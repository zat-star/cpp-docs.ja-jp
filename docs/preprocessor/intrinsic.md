---
title: "intrinsic | Microsoft Docs"
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
  - "intrinsic_CPP"
  - "vc-pragma.intrinsic"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "intrinsic プラグマ"
  - "プラグマ, intrinsic"
ms.assetid: 25c86ac7-ef40-47b7-a2c0-fada9c5dc3c5
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# intrinsic
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プラグマの引数リストで指定された関数の呼び出しが組み込みであることを指定します。  
  
## 構文  
  
```  
  
#pragma intrinsic( function1 [, function2, ...] )  
```  
  
## 解説  
 **intrinsic** プラグマは、関数の動作が既知であることをコンパイラに指示します。  コンパイラは、関数を呼び出し、より優れたパフォーマンスを得られる場合は、関数呼び出しをインライン命令に置き換えないことがあります。  
  
 組み込み形式のライブラリ関数を以下に示します。  コンパイラが **intrinsic** プラグマを検出した後、組み込み関数を含む最初の関数定義に達した時点でそのプラグマが有効になります。  その後、プラグマの効果は、ソース ファイルの最後まで、または同じ組み込み関数を指定した **function** プラグマが検出されるまで持続します。  **intrinsic** プラグマは、関数定義の外側でのみ \(グローバル レベルで\) 使用できます。  
  
 次の関数は、組み込み形式を持ち、その組み込み形式は [\/Oi](../Topic/-Oi%20\(Generate%20Intrinsic%20Functions\).md) を指定すると使用されます。  
  
|||||  
|-|-|-|-|  
|[\_disable](../intrinsics/disable.md)|[\_outp](../Topic/_outp,%20_outpw,%20_outpd.md)|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[strcmp](../Topic/strcmp,%20wcscmp,%20_mbscmp.md)|  
|[\_enable](../intrinsics/enable.md)|[\_outpw](../Topic/_outp,%20_outpw,%20_outpd.md)|[labs](../misc/labs-llabs.md)|[strcpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|  
|[\_inp](../c-runtime-library/inp-inpw-inpd.md)|[\_rotl](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|[strlen](../Topic/strlen,%20wcslen,%20_mbslen,%20_mbslen_l,%20_mbstrlen,%20_mbstrlen_l.md)|  
|[\_inpw](../c-runtime-library/inp-inpw-inpd.md)|[\_rotr](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)||  
|[\_lrotl](../c-runtime-library/reference/lrotl-lrotr.md)|[\_strset](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|[memset](../c-runtime-library/reference/memset-wmemset.md)||  
|[\_lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|[abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)||  
  
 組み込み関数を使うと、関数呼び出しのオーバーヘッドがなくなるためプログラムの実行速度は向上しますが、コードが追加されるためプログラムのサイズが大きくなる可能性があります。  
  
 **x86 固有の仕様→**  
  
 \_disable および \_enable 組み込み関数は、割り込みを無効または有効にするカーネル モード命令を生成するため、カーネル モード ドライバーで役立ちます。  
  
## 使用例  
 コマンド ラインで「cl \-c \-FAs sample.c」と入力して次のコードをコンパイルし、sample.asm を見て組み込み関数が x86 命令の CLI と STI になることを確認します。  
  
```  
// pragma_directive_intrinsic.cpp  
// processor: x86  
#include <dos.h>   // definitions for _disable, _enable  
#pragma intrinsic(_disable)  
#pragma intrinsic(_enable)  
void f1(void) {  
   _disable();  
   // do some work here that should not be interrupted  
   _enable();  
}  
int main() {  
}  
```  
  
 **End x86 固有の仕様**  
  
 次に示す浮動小数点関数には本物の組み込み形式はありません。  代わりに、引数をプログラム スタックにプッシュするのではなく、浮動小数点演算コプロセッサに直接渡すバージョンがあります。  
  
|||||  
|-|-|-|-|  
|[acos](../c-runtime-library/reference/acos-acosf-acosl.md)|[cosh](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|[pow](../Topic/pow,%20powf,%20powl.md)|[tanh](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|[fmod](../Topic/fmod,%20fmodf.md)|[sinh](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)||  
  
 次に示す小数点関数は、[\/Oi](../Topic/-Oi%20\(Generate%20Intrinsic%20Functions\).md)、[\/Og](../build/reference/og-global-optimizations.md)、および [\/fp:fast](../build/reference/fp-specify-floating-point-behavior.md) \(または \/Og を含むオプション、つまり、[\/Ox](../build/reference/ox-full-optimization.md)、[\/O1](../build/reference/o1-o2-minimize-size-maximize-speed.md)、\/O2\) を指定すると、本物の組み込み形式を持ちます。  
  
|||||  
|-|-|-|-|  
|[atan](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[exp](../c-runtime-library/reference/exp-expf.md)|[log10](../Topic/log,%20logf,%20log10,%20log10f.md)|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|  
|[atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[log](../Topic/log,%20logf,%20log10,%20log10f.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|[tan](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[cos](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)||||  
  
 [\/fp:strict](../build/reference/fp-specify-floating-point-behavior.md) または [\/Za](../build/reference/za-ze-disable-language-extensions.md) を使用して、本物の組み込み浮動小数点オプションの生成をオーバーライドできます。  浮動小数点関数はライブラリ ルーチンとして生成されます。これらのライブラリ ルーチンでは、引数はプログラム スタックにプッシュされずに、数値演算コプロセッサに直接渡されます。  
  
 ソース テキストのブロックで組み込み関数を有効または無効にする方法の詳細と例については、「[\#pragma function](../preprocessor/function-c-cpp.md)」を参照してください。  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)