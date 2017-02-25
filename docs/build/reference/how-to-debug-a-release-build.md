---
title: "方法 : リリース ビルドをデバッグする | Microsoft Docs"
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
helpviewer_keywords: 
  - "デバッグ [C++], リリース ビルド"
  - "リリース ビルド, デバッグ"
ms.assetid: d333e4d1-4e6c-4384-84a9-cb549702da25
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 方法 : リリース ビルドをデバッグする
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アプリケーションのリリース ビルドをデバッグできます。  
  
### リリース ビルドをデバッグするには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** ノードをクリックします。  **\[デバッグ情報の形式\]** を [&#91;C7 互換 \(\/Z7\)&#93;](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md) または **\[プログラム データベース \(\/Zi\)\]** に設定します。  
  
3.  **\[リンカー\]** を展開して **\[全般\]** ノードをクリックします。  **\[インクリメンタル リンクを有効にする\]** を [&#91;インクリメンタル リンクを行わない \(\/INCREMENTAL:NO\)&#93;](../../build/reference/incremental-link-incrementally.md) に設定します。  
  
4.  **\[デバッグ\]** ノードをクリックします。  **\[デバッグ情報の生成\]** を [&#91;はい \(\/DEBUG\)&#93;](../../build/reference/debug-generate-debug-info.md) に設定します。  
  
5.  **\[最適化\]** ノードをクリックします。  **\[参照\]** を [&#91;\/OPT:REF&#93;](../../build/reference/opt-optimizations.md) に、**\[COMDAT の圧縮\]** を [&#91;\/OPT:ICF&#93;](../../build/reference/opt-optimizations.md) に設定します。  
  
6.  これで、リリース ビルドのアプリケーションをデバッグできます。  問題の発生箇所を見つけるには、エラーが発生している個所までコードをステップ実行し \(または Just\-In\-Time デバッグを使用し\)、不正なパラメーターまたはコードを特定します。  
  
     アプリケーションがデバッグ ビルドでは動作してもリリース ビルドではエラーになる場合、コンパイラの最適化処理のいずれかがソース コード内の欠陥を検出している可能性があります。  問題を特定するには、ソース コード ファイルごとに選択した最適化を無効にし、その問題の原因であるファイルと最適化を見つけます \(このプロセスを高速化するには、まずすべてのファイルを 2 つのグループに分割して、1 つのグループの最適化を無効にし、そのグループに問題があれば、問題があるファイルを特定するまでそのグループの分割を続けます\)。  
  
     デバッグ ビルド内のこのようなバグを検出するには、[\/RTC](../../build/reference/rtc-run-time-error-checks.md) を使用できます。  
  
     詳細については、「[コードの最適化](../../build/reference/optimizing-your-code.md)」を参照してください。  
  
## 参照  
 [リリース ビルドの問題の解決](../../build/reference/fixing-release-build-problems.md)