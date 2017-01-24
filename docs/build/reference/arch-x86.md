---
title: "/arch (x86) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 9dd5a75d-06e4-4674-aade-33228486078d
caps.latest.revision: 33
caps.handback.revision: 33
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /arch (x86)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

x86 でコード生成のアーキテクチャを指定します。  「[\/arch \(x64\)](../../build/reference/arch-x64.md)」および「[\/arch \(ARM\)](../../build/reference/arch-arm.md)」も参照してください。  
  
## 構文  
  
```  
/arch:[IA32|SSE|SSE2|AVX|AVX2]  
```  
  
## 引数  
 **\/arch:IA32**  
 拡張命令なしを指定し、浮動小数点計算に x87 を指定します。  
  
 **\/arch:SSE**  
 SSE 命令の使用を有効にします。  
  
 **\/arch:SSE2**  
 SSE2 命令の使用を有効にします。  **\/arch** オプションが指定されていない場合、これは x86 プラットフォームの既定の命令になります。  
  
 **\/arch:AVX**  
 Advanced Vector Extensions 命令の使用を有効にします。  
  
 **\/arch:AVX2**  
 Advanced Vector Extensions 2 命令の使用を有効にします。  
  
## 解説  
 SSE 命令および SSE2 命令は、さまざまな Intel プロセッサおよび AMD プロセッサに組み込まれています。  AVX 命令は、Intel Sandy Bridge プロセッサおよび AMD Bulldozer プロセッサに組み込まれています。  AVX2 命令は、Intel Haswell および Broadwell プロセッサと AMD Excavator ベースのプロセッサでサポートされています。  
  
 `_M_IX86_FP`、`__AVX__`、および `__AVX2__` マクロは、**\/arch** コンパイラ オプションが使用された場合にどれが使用されたかを示します。  詳細については、「[定義済みマクロ](../../preprocessor/predefined-macros.md)」を参照してください。  **\/arch:AVX2** オプションと `__AVX2__` マクロは、Visual Studio 2013 更新プログラム 2、バージョン 12.0.34567.1 で導入されました。  
  
 **\/arch** を指定した場合、SSE 命令および SSE2 命令をいつどのように利用するかは、オプティマイザーによって選択されます。  SSE 命令と SSE2 命令は、x87 浮動小数点レジスタ スタックよりも SSE\/SSE2 命令およびレジスタを使用した方が高速であると判断された場合に、一部のスカラー浮動小数点演算に使用されます。  したがって、実際のコードでは、浮動小数点演算に x87 と SSE\/SSE2 の両方を組み合わせて使用してもかまいません。  また、**\/arch:SSE2** を指定した場合は、SSE2 命令を一部の 64 ビット整数演算に使用できます。  
  
 コンパイラでは、SSE 命令と SSE2 命令の使用に加え、SSE および SSE2 をサポートするプロセッサ リビジョンに組み込まれているその他の命令も使用します。  例としては、Intel プロセッサの Pentium Pro リビジョンで初めて導入された CMOV 命令が挙げられます。  
  
 x86 コンパイラは既定で SSE2 命令を使用するコードを生成するため、**\/arch:IA32** を指定して x86 プロセッサ用の SSE 命令と SSE2 命令の生成を無効にする必要があります。  
  
 **\/arch** はネイティブ関数のコード生成にのみ影響します。  [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) を指定してコンパイルした場合、**\/arch** はマネージ関数のコード生成に影響しません。  
  
 **\/arch** と [\/QIfist](../../build/reference/qifist-suppress-ftol.md) は、同じコンパイル単位では使用できません。  特に、ユーザーが `_controlfp` を使用して FP 制御ワードを変更しない場合、ランタイム スタートアップ コードでは x87 FPU 制御ワードの精度制御フィールドが 53 ビットに設定されます。  そのため、式内のすべての浮動小数点演算と倍精度浮動小数点演算は、53 ビットの有効桁と 15 ビットの指数部を使用します。  ただし、すべての SSE 単精度浮動小数点演算では、24 ビットの有効桁と 8 ビットの指数部が使用され、SSE2 倍精度浮動小数点演算では、53 ビットの有効桁と 11 ビットの指数部が使用されます。  詳細については、「[\_control87、\_controlfp、\_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md)」を参照してください。  これらの差異は、ユーザーの代入が各部分式の後に行われる場合ではなく、単一の式ツリー内で発生する可能性があります。  次に例を示します。  
  
```c  
  
r = f1 * f2 + d;  // Different results are possible on SSE/SSE2.  
```  
  
 以下と比較してください。  
  
```c  
  
t = f1 * f2;   // Do f1 * f2, round to the type of t.  
r = t + d;     // This should produce the same overall result   
               // whether x87 stack is used or SSE/SSE2 is used.  
```  
  
### AVX、AVX2、IA32、SSE、または SSE2 のこのコンパイラ オプションを Visual Studio で設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[構成プロパティ\]**、**\[C\/C\+\+\]** フォルダーを選択します。  
  
3.  **\[コード生成\]** プロパティ ページを選択します。  
  
4.  **\[拡張命令セットを有効にする\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>」を参照してください。  
  
## 参照  
 [\/arch \(最小限の CPU アーキテクチャ\)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)