---
title: "致命的なエラー C1084 | Microsoft Docs"
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
  - "C1084"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1084"
ms.assetid: b2f273ef-3a14-4d5f-8ce0-7a11a0388fe6
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 致命的なエラー C1084
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

filetype ファイルを読み取れません。'file': message  
  
 このエラーは一般的に、コンパイラによって行われた内部的なシステム API 呼び出しの失敗によって発生します。  このエラーが発生したときに表示されるメッセージは、多くの場合、[\_wcserror\_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md) または [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351.aspx) によって生成されます。  
  
 次の手順を実行すると、C1084 の解決に役立つ場合があります。  
  
-   指定したファイルが存在することを確認します。  
  
-   指定したファイルにアクセスするための適切なアクセス許可が設定されていることを確認します。  
  
-   コマンド ライン構文が「[コンパイラ コマンド ラインの構文](../../build/reference/compiler-command-line-syntax.md)」で説明されている規則に従っていることを確認します。  
  
-   環境変数 **TMP** および **TEMP** が適切に設定されていること、およびこれらの環境変数で参照されるディレクトリにアクセスするための適切なアクセス許可が設定されていることを確認します。  また、**TMP** および **TEMP** 環境変数で参照されるドライブに、十分な空き領域があることを確認します。  
  
-   "ファイル番号が正しくありません" というメッセージが表示される場合は、指定したファイルがバックグラウンドでのコンパイル中にフォアグラウンドで閉じられている可能性があります。  
  
 上記の診断を実行した後、クリーン ビルドを実行します。