---
title: "C ランタイム エラー R6016 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6016"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6016"
ms.assetid: 7bd3f274-d9c4-4bc4-8252-80bf168c4c3a
caps.latest.revision: 12
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C ランタイム エラー R6016
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

not enough space for thread data  
  
> [!NOTE]
>  このエラー メッセージが表示された場合、名前付きプログラムは、内部メモリの問題が原因でシャットダウンしました。  このエラーにはさまざまな原因が考えられますが、その多くは、プログラムの問題、またはプログラムによって使用される Visual C\+\+ ライブラリの破損が原因で発生しています。  
>   
>  このエラーを解決するには、次の手順を試してみます。  
>   
>  -   **\[コントロール パネル\]** の **\[プログラムと機能\]** ページを使用して、プログラムを修復または再インストールする。  
> -   **\[コントロール パネル\]** の **\[プログラムと機能\]** ページを使用して、Microsoft Visual C\+\+ 再頒布可能パッケージのすべてのコピーを修復または再インストールする。  
> -   **\[コントロール パネル\]** の **\[Windows Update\]** でソフトウェア更新プログラムを確認する。  
> -   プログラムの更新バージョンを確認する。  
  
 このエラーは、[\_beginthread](../Topic/_beginthread,%20_beginthreadex.md) 呼び出しまたは `_beginthreadex` 呼び出しを完了するのに十分なメモリをオペレーティング システムから受け取らなかった、またはスレッド ローカル ストレージが、 `_beginthread` または `_beginthreadex` によって初期化されていなかったことが原因で発生します。  
  
 新規スレッドの開始時、ライブラリは、そのスレッド用に新しい内部データベースを生成する必要があります。  オペレーティング システムのメモリを使用してデータベースを展開できないと、スレッドは開始されず、スレッドの呼び出しプロセスは停止します。  これは、プロセスによって作成されたスレッドが多すぎる場合、またはスレッド ローカル ストレージが不足している場合に発生する可能性があります。  
  
 C ランタイム ライブラリ \(CRT\) を呼び出す実行可能ファイルでは、Windows API `CreateThread` ではなく、スレッド作成用の `_beginthreadex` を使用することをお勧めします。  `_beginthreadex` は、スレッド ローカル ストレージで多くの CRT 関数によって使用される内部静的ストレージを初期化します。  `CreateThread` を使用してスレッドを作成すると、初期化された静的内部ストレージを必要とする CRT 関数が呼び出されたときに、R6016 でプロセスが終了する場合があります。