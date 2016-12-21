---
title: "/FD (IDE の簡易リビルド) | Microsoft Docs"
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
  - "/FD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FD コンパイラ オプション [C++]"
  - "FD コンパイラ オプション [C++]"
  - "-FD コンパイラ オプション [C++]"
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FD (IDE の簡易リビルド)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/FD** は、ユーザーに公開されません。ただし、例外として、[\/Gm \(簡易リビルドの有効化\)](../../build/reference/gm-enable-minimal-rebuild.md) が選択されていない場合に限り、C\+\+ プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスの [&#91;コマンド ライン&#93;](../../ide/command-line-property-pages.md) プロパティ ページに公開されます。  **\/FD** は、開発環境以外の環境では無効です。  **\/FD** は **cl \/?** の出力には公開されません。  
  
 開発環境で **\/Gm** を有効にしない場合は、**\/FD** が使用されます。  **\/FD** は、十分な依存関係情報が .idb ファイルに確実に含まれるようにします。  **\/FD** は開発環境でのみ使用し、コマンド ラインやビルド スクリプトからは使用しないでください。  
  
## 参照  
 [出力ファイル \(\/F\) オプション](../../build/reference/output-file-f-options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)