---
title: "/GT (スレッド ローカル ストレージを使用したファイバー保護のサポート) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.EnableFiberSafeOptimizations"
  - "/gt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GT コンパイラ オプション [C++]"
  - "ファイバー保護 (静的スレッド ローカル ストレージを使用した) コンパイラ オプション [C++]"
  - "GT コンパイラ オプション [C++]"
  - "-GT コンパイラ オプション [C++]"
  - "静的スレッド ローカル ストレージとファイバー保護"
  - "スレッド ローカル ストレージ"
ms.assetid: 071fec79-c701-432b-9970-457344133159
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /GT (スレッド ローカル ストレージを使用したファイバー保護のサポート)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

静的スレッド ローカル ストレージに割り当てられたデータ、つまり `__declspec(thread)` で割り当てられたデータに対して、ファイバー保護をサポートします。  
  
## 構文  
  
```  
/GT  
```  
  
## 解説  
 `__declspec(thread)` を使って宣言されたデータは、スレッド ローカル ストレージ \(TLS: Thread\-Local Storage\) の配列を通じて参照されます。  TLS 配列とは、スレッドごとにシステムで維持されるアドレスの配列です。  この配列の各アドレスは、スレッド ローカル ストレージのデータ位置を示します。  
  
 ファイバーは、軽量オブジェクトです。スタックとレジスタのコンテキストから構成され、さまざまなスレッドでスケジュールできます。  ファイバーは、どのスレッドでも動作可能です。  ファイバーはスワップ アウト後に別のスレッドで再起動されることがあるため、関数呼び出しにわたる共通の部分式として TLS 配列のアドレスをキャッシュしたり最適化したりしないでください。詳細については、「[\/Og \(グローバルの最適化\)](../../build/reference/og-global-optimizations.md) オプション」に関するトピックを参照してください。  **\/GT** は、このような最適化を抑止します。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[最適化\]** プロパティ ページをクリックします。  
  
4.  **\[ファイバー保護の最適化\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFiberSafeOptimizations%2A>」を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)