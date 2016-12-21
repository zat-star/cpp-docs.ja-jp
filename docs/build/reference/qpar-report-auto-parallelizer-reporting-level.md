---
title: "/Qpar-report (自動並行化レポート作成レベル) | Microsoft Docs"
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
ms.assetid: 562673b9-02da-4bf8-bb64-70bc25ef4651
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Qpar-report (自動並行化レポート作成レベル)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンパイラの[自動並列化](../../parallel/auto-parallelization-and-auto-vectorization.md)レポート機能を有効にし、コンパイル時の出力の情報メッセージのレベルを指定します。  
  
## 構文  
  
```  
/Qpar-report:{1}{2}  
```  
  
## 解説  
 **\/Qpar\-report:1**  
 並列化されたループに対する情報メッセージを出力します。  
  
 **\/Qpar\-report:2**  
 並列化されたループと並列化されていないループの情報メッセージを理由コードと共に出力します。  
  
 メッセージは stdout に報告されます。  情報メッセージが報告されない場合、コードにループが含まれていないか、並列化されていないループが報告されるようにレポートのレベルが設定されていませんでした。  理由コードとメッセージの詳細については、"[ベクター化と並列化のメッセージ ](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md) \(ベクター化\/並行化のメッセージ\)"を参照してください。  
  
### \/Qpar\-report コンパイラ オプションを Visual Studio で設定するには  
  
1.  **ソリューション エクスプローラー**で、プロジェクトのショートカット メニューを開き、**\[プロパティ\]** をクリックします。  
  
2.  **\[プロパティ ページ\]** ダイアログ ボックスで、**\[C\/C\+\+\]** の下の **\[コマンド ライン\]** を選択します。  
  
3.  **\[追加のオプション\]** ボックスで、「`/Qpar-report:1`」または「`/Qpar-report:2`」と入力します。  
  
### \/Qpar\-report コンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> のコード例を使用してください。  
  
## 参照  
 [\/Q オプション \(低水準の操作\)](../../build/reference/q-options-low-level-operations.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)   
 [Parallel Programming in Native Code \(ネイティブ コードでの並列プログラミング\)](http://go.microsoft.com/fwlink/?LinkId=263662)