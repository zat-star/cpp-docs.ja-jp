---
title: "自動並行化と自動ベクター化 | Microsoft Docs"
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
ms.assetid: ec71583a-287b-4599-8767-1d255e080fe3
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 自動並行化と自動ベクター化
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

自動並行化と自動ベクター化は、コード内のループのパフォーマンスが自動的に向上するように設計されています。  
  
## 自動並行化  
 [\/Qpar](../Topic/-Qpar%20\(Auto-Parallelizer\).md) コンパイラ スイッチは、コード内のループの*自動並行化*を有効にします。  既存のコードを変更せずにこのフラグを指定すると、並行化の利点を達成できる可能性があるループを見つける観点で、コンパイラがコードを評価します。  つまり、処理量がそれほど多くなく、したがって並行化の利点が多くないループを見つける可能性があります。また、不必要な並行化はいずれも、パフォーマンスの向上ではなく低下につながる可能性のあるスレッド プール、余分の同期、または他のプロセスの発生源になる可能性があります。したがって、コンパイラは並行化するループを保守的な基準で選択します。  たとえば、コンパイル時にループの上限が不明である次の例について考えてみましょう。  
  
```cpp  
  
void loop_test(int u) {  
   for (int i=0; i<u; ++i)  
      A[i] = B[i] * C[i];  
}  
```  
  
 `u` は小さい値という可能性があるため、コンパイラは自動的にこのループを並行化することはありません。  ただし、`u` が必ず大きいことを把握している場合は、開発者が並行化を希望することもあります。  自動並行化を有効にするには、[\#pragma loop\(hint\_parallel\(n\)\)](../../preprocessor/loop.md) を指定します。ここで、`n` は、並行化するスレッドの数です。  次の例では、コンパイラは 8 つのスレッドにまたがるループの並行化を試みます。  
  
```cpp  
  
void loop_test(int u) {  
#pragma loop(hint_parallel(8))  
   for (int i=0; i<u; ++i)  
      A[i] = B[i] * C[i];  
}  
```  
  
 他のすべての [pragma ディレクティブ](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)と同様に、代替 pragma 構文`__pragma(loop(hint_parallel(n)))`もサポートされています。  
  
 開発者が希望しても、コンパイラが並行化できないループが存在します。  次に例を示します。  
  
```cpp  
  
#pragma loop(hint_parallel(8))  
for (int i=0; i<upper_bound(); ++i)  
    A[i] = B[i] * C[i];  
```  
  
 関数の `upper_bound()` が、呼び出されるたびに変化する可能性がある場合。  上限を特定できないため、コンパイラはこのループを並行化できない理由を説明する診断メッセージを生成できます。  次の例では、並行化できるループ、並行化できないループ、コマンド プロンプトで使用するためのコンパイラの構文、および各コマンド ライン オプションに対応するコンパイラ出力を示します。  
  
```cpp  
int A[1000];  
void test() {  
#pragma loop(hint_parallel(0))  
    for (int i=0; i<1000; ++i) {  
        A[i] = A[i] + 1;  
    }  
  
    for (int i=1000; i<2000; ++i) {  
        A[i] = A[i] + 1;  
    }  
}  
  
```  
  
 次のコマンドを使用してコンパイル:  
  
 **cl d:\\myproject\\mylooptest.cpp \/O2 \/Qpar \/Qpar\-report:1**  
  
 生成される出力:  
  
 **\-\-\- Analyzing function: void \_\_cdecl test\(void\)**   
  **d:\\myproject\\mytest.cpp\(4\) : loop parallelized**  
  
 次のコマンドを使用してコンパイル:  
  
 **cl d:\\myproject\\mylooptest.cpp \/O2 \/Qpar \/Qpar\-report:2**  
  
 生成される出力:  
  
 **\-\-\- Analyzing function: void \_\_cdecl test\(void\)**   
  **d:\\myproject\\mytest.cpp\(4\) : loop parallelized**   
  **d:\\myproject\\mytest.cpp\(4\) : loop not parallelized due to reason '1008'**  
  
 2 つの異なる [\/Qpar\-report \(自動並行化レポート作成レベル\)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md) オプションの間での出力の違いに注意してください。  **\/Qpar\-report:1** を指定した場合は、正常に並行化されたループのみに関する並行化メッセージが出力されます。  **\/Qpar\-report:2** を指定した場合は、並行化したループと並行化しなかったループの両方に関する並行化メッセージが出力されます。  
  
 理由コードとメッセージの詳細については、「[ベクター化と並列化のメッセージ ](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)」を参照してください。  
  
## 自動ベクター化  
 自動ベクター化機能は、コード内のループを分析し、可能な場合は、ターゲット コンピューター上のベクター レジスタとベクター命令を使用してそれらのループを実行します。  この方法により、コードのパフォーマンスが向上する可能性があります。  コンパイラは、[\/arch](../../build/reference/arch-minimum-cpu-architecture.md) スイッチに従って、Intel または AMD プロセッサの SSE2、AVX、AVX2 命令、あるいは ARM プロセッサの NEON 命令を対象とします。  
  
 自動ベクター化機能は、**\/arch** スイッチで指定されていない命令を生成することもあります。  これらの命令は、実行時チェックによって保護され、引き続きコードが正しく実行されることが確認されます。  たとえば、**\/arch:SSE2** のコンパイル時に SSE4.2 命令が送出されることがあります。  実行時チェックによって、ターゲット プロセッサで SSE4.2 を使用できるかが確認され、プロセッサがそれらの命令をサポートしていない場合は SSE4.2 でないバージョンのループにジャンプします。  
  
 既定では、自動ベクター化が有効になります。  ベクター化対象のコードのパフォーマンスを比較しようとする場合は、特定のループのベクター化を無効にするために、[\#pragma loop\(no\_vector\)](../../preprocessor/loop.md) を使用できます。  
  
```  
  
#pragma loop(no_vector)  
for (int i = 0; i < 1000; ++i)  
   A[i] = B[i] + C[i];  
  
```  
  
 他のすべての [pragma ディレクティブ](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)と同様に、代替 pragma 構文`__pragma(loop(no_vector))`もサポートされています。  
  
 自動並行化と同様に、[\/Qvec\-report \(自動ベクター化レポート作成レベル\)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md) コマンドライン オプションを指定し、正常にベクター化したループのみを報告する \(**\/Qvec\-report:1**\)か、ベクター化したループとベクター化しなかったループの両方を報告する \(**\/Qvec\-report:2**\) ことができます。  
  
 理由コードとメッセージの詳細については、「[ベクター化と並列化のメッセージ ](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)」を参照してください。  
  
 ベクター化機能が実際にどのように動作するかを示す例については、「[Project Austin Part 2 of 6: Page Curling](http://blogs.msdn.com/b/vcblog/archive/2012/09/27/10348494.aspx)」を参照してください。  
  
## 参照  
 [ループ](../../preprocessor/loop.md)   
 [ネイティブ コードでの並行プログラミング](http://go.microsoft.com/fwlink/?LinkId=263662)   
 [\/Qpar \(自動並行化\)](../Topic/-Qpar%20\(Auto-Parallelizer\).md)   
 [\/Qpar\-report \(自動並行化レポート作成レベル\)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)   
 [\/Qvec\-report \(自動ベクター化レポート作成レベル\)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md)   
 [ベクター化と並列化のメッセージ ](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)