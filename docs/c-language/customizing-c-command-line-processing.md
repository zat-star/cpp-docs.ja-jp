---
title: "コマンド ライン パラメーターの処理 | Microsoft Docs"
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
  - "_exec 関数"
  - "_setargv 関数"
  - "_spawn 関数"
  - "コマンド ライン, 処理"
  - "コマンド ライン, 引数の処理"
  - "コマンドライン処理"
  - "環境, 環境処理ルーチン"
  - "スタートアップ コード, コマンドライン処理のカスタマイズ"
  - "環境処理の抑制"
ms.assetid: c20fa11d-b35b-4f3e-93b6-2cd5a1c3c993
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# コマンド ライン パラメーターの処理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プログラムがコマンド ラインの引数を受け取らない場合は、コマンド ライン処理を実行するライブラリ ルーチンの使用を制約することで、領域を節約できます。  このルーチンは、「[ワイルドカード引数の展開](../Topic/Expanding%20Wildcard%20Arguments.md)」で説明されているように、**\_setargv** \(ワイド文字環境では **\_wsetargv**\) と呼ばれます。  使用を抑制するには、**main** 関数を含むファイルの中に何も実行しないルーチンを定義し、**\_setargv** \(ワイド文字環境の場合は **\_wsetargv**\) という名前を付けます。  これにより、**\_setargv** または **\_wsetargv** の呼び出しが **\_setargv** または **\_wsetargv** の定義によって満たされるため、ライブラリ バージョンは読み込まれません。  
  
 同様に、`envp` 引数を使用して環境テーブルにアクセスしない場合は、環境処理ルーチンである **\_setenvp** \(または **\_wsetenvp**\) の代わりに独自の空ルーチンを指定できます。  
  
 プログラムが C ランタイム ライブラリ ルーチンの **\_spawn** または **\_exec** ファミリを呼び出す場合、起動元のプロセスから新しいプロセスに環境を渡すためにこのルーチンが使用されているので、環境処理ルーチンを抑制しないでください。  
  
## 参照  
 [main 関数とプログラム実行](../c-language/main-function-and-program-execution.md)