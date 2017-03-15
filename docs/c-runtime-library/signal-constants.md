---
title: "signal 定数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SIGTERM"
  - "SIGFPE"
  - "SIGABRT"
  - "SIGILL"
  - "SIGINT"
  - "SIGSEGV"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SIGABRT 定数"
  - "SIGFPE 定数"
  - "SIGILL 定数"
  - "SIGINT 定数"
  - "signal 定数"
  - "SIGSEGV 定数"
  - "SIGTERM 定数"
ms.assetid: a3b39281-dae7-4e44-8d68-e6a610c669dd
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# signal 定数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
#include <signal.h>  
```  
  
## 解説  
 `sig` の引数には、次に示すマニフェスト定数の 1 つが必要があります \(SIGNAL.H\) で定義されます。  
  
 `SIGABRT`  
 中止。  既定のアクションは終了コード 3.、呼び出し元のプログラムを終了します。  
  
 `SIGABRT_COMPAT`  
 SIGABRT と同じです。  他のプラットフォームとの互換性のためにあります。  
  
 `SIGFPE`  
 オーバーフロー、ゼロによる除算、無効な操作などの浮動小数点エラー。  既定のアクションは、呼び出し元のプログラムを終了します。  
  
 `SIGILL`  
 違法順序。  既定のアクションは、呼び出し元のプログラムを終了します。  
  
 `SIGINT`  
 Ctrl \+ C 割り込み。  既定のアクションは終了コード 3.、呼び出し元のプログラムを終了します。  
  
 `SIGSEGV`  
 無効なストレージにアクセスします。  既定のアクションは、呼び出し元のプログラムを終了します。  
  
 `SIGTERM`  
 プログラム終了要求に送信されます。  既定のアクションは終了コード 3.、呼び出し元のプログラムを終了します。  
  
 `SIG_ERR`  
 エラーを示すシグナルの戻り値の型が発生しました。  
  
## 参照  
 [signal](../c-runtime-library/reference/signal.md)   
 [raise](../c-runtime-library/reference/raise.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)