---
title: "C++ コマンド ライン処理のカスタマイズ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_setenvp"
  - "_setargv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_setargv 関数"
  - "_setenvp 関数"
  - "コマンド ライン, 処理"
  - "コマンド ライン, 引数の処理"
  - "コマンドライン処理"
  - "環境, 環境処理ルーチン"
  - "スタートアップ コード, コマンドライン処理のカスタマイズ"
  - "環境処理の抑制"
ms.assetid: aae01cbb-892b-48b8-8e1f-34f22421f263
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ コマンド ライン処理のカスタマイズ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 プログラムがコマンド ラインの引数を受け取らない場合は、コマンド ライン処理を実行するライブラリ ルーチンの使用を制約することで、領域を節約できます。  このルーチンは **\_setargv** と呼ばれ、「[ワイルドカードの展開](../cpp/wildcard-expansion.md)」で説明されています。  使用を抑制するには、**main** 関数を含むファイルの中に何も実行しないルーチンを定義し、**\_setargv** という名前を付けます。  これにより、**\_setargv** の呼び出しが **\_setargv** の定義によって満たされるため、ライブラリ バージョンは読み込まれません。  
  
 同様に、`envp` 引数を使用して環境テーブルにアクセスしない場合は、環境処理ルーチンである **\_setenvp** に独自の空ルーチンを指定できます。  **\_setargv** 関数と同様、**\_setenvp** が **extern "C"** として宣言される必要があります。  
  
 プログラムは、C ランタイム ライブラリでルーチンの **spawn** ファミリまたは `exec` ファミリを呼び出すことがあります。  この場合、このルーチンは親プロセスから子プロセスに環境を渡すために使用されるため、環境処理ルーチンを抑制しないでください。  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [main: プログラムの起動](../Topic/main:%20Program%20Startup.md)