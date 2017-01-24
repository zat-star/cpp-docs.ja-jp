---
title: "国際化のアプローチ | Microsoft Docs"
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
helpviewer_keywords: 
  - "文字セット [C++], 国際対応プログラミング戦略"
  - "グローバリゼーション [C++], 文字セット"
  - "言語の移植性が高いコード [C++]"
  - "ローカリゼーション [C++], 文字セット"
  - "MBCS [C++], 国際対応戦略"
  - "Unicode [C++], グローバル化 (アプリケーションを)"
  - "Win32 [C++], 国際対応プログラミング戦略"
  - "Windows API [C++], 国際対応プログラミング戦略"
ms.assetid: b09d9854-0709-4b9a-a00c-b0b8bc4199b1
caps.latest.revision: 8
caps.handback.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# 国際化のアプローチ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

国際市場を視野に入れた場合、ターゲットとするオペレーティング システムと市場に応じて、さまざまなアプローチが考えられます。  
  
-   Unicode を採用し、オーバーヘッドなしに Windows 2000 と Windows NT 上で実行できるようにする。この場合、Windows 95 や Windows 98 では実行できません。  
  
     Unicode 固有の機能を使用し、文字はすべて 16 ビット幅とします。目的に応じてプログラムの一部に ANSI 文字を使用してもかまいません。  C のランタイム ライブラリには、Unicode だけを使ったプログラミングに適した関数、マクロ、およびデータ型が用意されています。  MFC は、Unicode を完全にサポートしています。  
  
-   MBCS を採用し、すべての Win32 プラットフォームで動作できるようにする。  
  
     MBCS 固有の機能を使用します。  文字列は、1 バイト文字だけでも、2 バイト文字だけでも構成できます。また、両方を混在させることもできます。  C のランタイム ライブラリには、MBCS だけを使ったプログラミングに適した関数、マクロ、およびデータ型が用意されています。  MFC は、MBCS を完全にサポートしています。  
  
-   **\_UNICODE** シンボルまたは **\_MBCS** シンボルを定義して再コンパイルすることにより、アプリケーションのソース コードの移植性を高める。いずれのシンボルを使用するアプリケーションも作成できます。  詳細については、「[Tchar.h における汎用テキストのマッピング](../Topic/Generic-Text%20Mappings%20in%20Tchar.h.md)」を参照してください。  
  
-   アプリケーションは、Windows 95、Windows 98、および Windows の Unicode ラッパー ライブラリがない関数が記述されているように、My を使用します [Windows 98 と Windows 2000 の両方で動作する Unicode 一つのアプリケーションをデザインします。](http://go.microsoft.com/fwlink/p/?LinkId=250770)。  ラッパー ライブラリは購入することもできます。  
  
     完全に移植性のある C のランタイム関数や、マクロ、データ型を使います。  MFC は柔軟性に富み、これらを問題なくサポートします。  
  
 残りのトピックでは、Unicode または MBCS としてビルドできる完全に移植可能なコードの記述について重点的に説明します。  
  
## 参照  
 [Unicode と MBCS](../text/unicode-and-mbcs.md)   
 [ロケールとコード ページ](../text/locales-and-code-pages.md)