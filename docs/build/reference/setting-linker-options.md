---
title: "リンカー オプションの設定 | Microsoft Docs"
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
  - "ファイル [C++], LINK"
  - "入力ファイル [C++]"
  - "入力ファイル [C++], リンカー"
  - "リンカー [C++], スイッチ"
  - "リンカー [C++], 方法 (オプション設定の)"
  - "オブジェクト/ライブラリ モジュール"
ms.assetid: e08fb487-0f2e-4f24-87db-232dbc8bd2e2
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# リンカー オプションの設定
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

リンカー オプションは、開発環境の内部でも外部でも設定できます。  開発環境での設定方法は、リンカーの各オプションのトピックで説明します。  全オプションの一覧については、「[リンカー オプション](../../build/reference/linker-options.md)」を参照してください。  
  
 開発環境外で LINK を実行する場合、次のいずれかで入力を指定できます。  
  
-   [コマンド ライン](../../build/reference/linker-command-line-syntax.md)  
  
-   [コマンド ファイル](../../build/reference/link-command-files.md)  
  
-   [環境変数](../../build/reference/link-environment-variables.md)  
  
 リンク時は、まず環境変数 LINK で指定したオプションが処理されます。次にコマンド ラインで指定したオプション、最後にコマンド ファイルで指定したオプションが指定の順で処理されます。  同じオプションを引数を変えて繰り返し指定すると、最後に指定されたオプションが優先されます。  
  
 オプションはビルド全体に適用されます。オプションを特定の入力ファイルだけに適用させることはできません。  
  
## 参照  
 [C\/C\+\+ ビルドのリファレンス](../Topic/C-C++%20Building%20Reference.md)   
 [リンカー オプション](../../build/reference/linker-options.md)