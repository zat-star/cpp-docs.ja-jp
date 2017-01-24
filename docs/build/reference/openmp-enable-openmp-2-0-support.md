---
title: "/openmp (OpenMP 2.0 サポートの有効化) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/openmp"
  - "VC.Project.VCCLCompilerTool.OpenMP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/openmp コンパイラ オプション [C++]"
  - "-openmp コンパイラ オプション [C++]"
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /openmp (OpenMP 2.0 サポートの有効化)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`#pragma` [omp](../../preprocessor/omp.md) を処理するようにコンパイラに指示します。  
  
## 構文  
  
```  
/openmp  
```  
  
## 解説  
 `#pragma omp` は、[Directives](../../parallel/openmp/reference/openmp-directives.md) および [Clauses](../../parallel/openmp/reference/openmp-clauses.md) を指定するために使用されます。  コンパイルで **\/openmp** が指定されていない場合、コンパイラは OpenMP 句および OpenMP ディレクティブを無視します。  [OpenMP Function](../../parallel/openmp/reference/openmp-functions.md) 呼び出しは、**\/openmp** が指定されていない場合でもコンパイラで処理されます。  
  
 **\/openmp** でコンパイルされ、[Libraries](../../parallel/openmp/reference/openmp-libraries.md) を使用するアプリケーションは、Windows 2000 以降のオペレーティング システムでのみ実行できます。  
  
 **\/openmp** および **\/clr** を指定してコンパイルされたアプリケーションは、単一のアプリケーション ドメイン プロセスでのみ実行できます。複数のアプリケーション ドメインはサポートされていません。  つまり、モジュール コンストラクター \(.cctor\) は、実行時に、プロセスのコンパイルで **\/openmp** が指定されているかどうか、およびアプリケーションを既定以外のランタイムに読み込もうとしているかどうかを検出します。  詳細については、「[appdomain](../Topic/appdomain.md)」、「[\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md)」、および「[混在アセンブリの初期化](../Topic/Initialization%20of%20Mixed%20Assemblies.md)」を参照してください。  
  
 **\/openmp** および **\/clr** を指定してコンパイルされたアプリケーションを既定以外のアプリケーション ドメインに読み込もうとすると、<xref:System.TypeInitializationException> 例外がデバッガーの外部でスローされ、OpenMPWithMultipleAppdomainsException 例外がデバッガーでスローされます。  
  
 これらの例外は、次の場合にも発生することがあります。  
  
-   プロセスが **\/openmp** を指定してコンパイルされたアプリケーションを含めている、既定以外のアプリケーション ドメインに、**\/clr** を指定し **\/openmp** を指定しないでコンパイルされたアプリケーションが読み込まれている場合。  
  
-   **\/clr** アプリケーションを regasm.exe \([Regasm.exe \(アセンブリ登録ツール\)](../Topic/Regasm.exe%20\(Assembly%20Registration%20Tool\).md)\) などのユーティリティに渡し、そのユーティリティがその対象アセンブリを既定以外のアプリケーション ドメインに読み込む場合。  
  
 共通言語ランタイムのコード アクセス セキュリティは、OpenMP 領域では機能しません。  CLR コード アクセス セキュリティ属性を並列領域外で適用する場合、この属性は並列領域内では有効になりません。  
  
 Microsoft では、<xref:System.Security.AllowPartiallyTrustedCallersAttribute> または任意の CLR コード アクセス セキュリティ属性を使用して部分的に信頼される呼び出し元を許可する **\/openmp** アプリケーションを作成しないことをお勧めします。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[構成プロパティ\]** ノードを展開します。  
  
3.  **\[C\/C\+\+\]** ノードを展開します。  
  
4.  **\[言語\]** プロパティ ページをクリックします。  
  
5.  **\[OpenMP サポート\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>」を参照してください。  
  
## 使用例  
 次の例は、スレッドプールを起動時と起動後に使用した効果をいくつか比較しています。  x64、シングル コア、デュアル プロセッサの場合、スレッドプールの起動に 16 ミリ秒かかります。  しかし、その後のスレッドプールの使用にかかる時間はごくわずかです。  
  
 **\/openmp** を指定してコンパイルした場合、test2 への 2 回目の呼び出しは、スレッドプールの起動がないので、**\/openmp\-** を指定してコンパイルした場合よりも実行時間が長くなることはありません。  100 万回反復すると、test2 の 2 回目の呼び出しで **\/openmp** バージョンは **\/openmp\-** バージョンよりも高速になります。25 回の反復では、**\/openmp\-** バージョンも **\/openmp** バージョンもクロック単位より小さくなります。  
  
 したがって、アプリケーション内のループが 1 つだけで、その実行時間が 15 ミリ秒未満 \(コンピューターのオーバーヘッドの概算により変わる\) である場合は、**\/openmp** は適していないことがありますが、それより長い場合は、**\/openmp** の使用を検討します。  
  
```  
// cpp_compiler_options_openmp.cpp  
#include <omp.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <windows.h>  
  
volatile DWORD dwStart;  
volatile int global = 0;  
  
double test2(int num_steps) {  
   int i;  
   global++;  
   double x, pi, sum = 0.0, step;  
  
   step = 1.0 / (double) num_steps;  
  
   #pragma omp parallel for reduction(+:sum) private(x)  
   for (i = 1; i <= num_steps; i++) {  
      x = (i - 0.5) * step;  
      sum = sum + 4.0 / (1.0 + x*x);  
   }  
  
   pi = step * sum;  
   return pi;  
}  
  
int main(int argc, char* argv[]) {  
   double   d;  
   int n = 1000000;  
  
   if (argc > 1)  
      n = atoi(argv[1]);  
  
   dwStart = GetTickCount();  
   d = test2(n);  
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);  
  
   dwStart = GetTickCount();  
   d = test2(n);  
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);  
}  
```  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)