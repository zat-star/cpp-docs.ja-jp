---
title: "/Qvec-report (自動ベクター化レポート作成レベル) | Microsoft Docs"
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
ms.assetid: 4778c9a3-0692-4085-9b05-1bfeadf4c74a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Qvec-report (自動ベクター化レポート作成レベル)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンパイラ [自動Vectorizer](../../parallel/auto-parallelization-and-auto-vectorization.md) レポート機能を使用すると、出力にコンパイル中の情報メッセージのレベルを指定します。  
  
## 構文  
  
```  
/Qvec-report:{1}{2}  
```  
  
## 解説  
 **\/Qvec\-report:1**  
 vectorized であるループの情報メッセージを出力します。  
  
 **\/Qvec\-report:2**  
 理由コードとともに vectorized であると vectorized でないループの情報メッセージ ループを出力します。  
  
 理由コードとメッセージについては、[ベクター化と並列化のメッセージ ](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)を参照してください。  
  
### Visual Studio で \/Qvec\-report コンパイラ オプションを設定するには  
  
1.  **\[ソリューション エクスプローラー\]** で、プロジェクトのショートカット メニューを開き、**\[プロパティ\]** をクリックします。  
  
2.  **\[プロパティ ページ\]** ダイアログ ボックスで、**\[C\/C\+\+\]** で、**\[コマンド ライン\]** を選択します。  
  
3.  **\[追加オプション\]** ボックスで、`/Qvec-report: 1` または `/Qvec-report: 2`を入力します。  
  
### \/Qvec\-report コンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>でコード例を使用します。  
  
## 参照  
 [\/Q オプション \(低水準の操作\)](../../build/reference/q-options-low-level-operations.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)   
 [Parallel Programming in Native コード](http://go.microsoft.com/fwlink/?LinkId=263662)