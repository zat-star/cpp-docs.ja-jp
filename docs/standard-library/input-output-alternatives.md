---
title: "入出力の代替手段 | Microsoft Docs"
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
  - "I/O [C++], 代替"
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 入出力の代替手段
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ では、I\/O のプログラミングに複数の方法を提供し、T:  
  
-   直接 C ランタイム ライブラリいない I\/O。  
  
-   ANSI C ランタイム ライブラリの I\/O ストリーム。  
  
-   コンソールと直接 I\/O ポート。  
  
-   Microsoft Foundation Class ライブラリ。  
  
-   Microsoft C\+\+ の標準ライブラリ。  
  
 iostream クラスはバッファリングされたで役立ちます、書式設定されたテキスト I\/O です。  これらは、.の C\+\+ プログラミング インターフェイスを必要とし、Microsoft Foundation Class \(MFC\) ライブラリを使用しない場合、いないか、バイナリ I\/O でも役立ちます。  iostream クラスは、C ランタイム関数オブジェクト指向 I\/O の方法です。  
  
 Microsoft Windows オペレーティング システムに iostream クラスを使用できます。  文字列とファイル ストリームは制限なく機能しますが、文字モードのストリーム オブジェクト `cin`、`cout`、`cerr`と `clog` は Windows のグラフィカル ユーザー インターフェイスと矛盾しています。  また Windows 環境と直接やり取りするカスタム ストリーム クラスを派生できます。  
  
## 参照  
 [ストリームとは何か](../standard-library/what-a-stream-is.md)