---
title: "プロジェクトでのプリコンパイル済みヘッダーの使用 | Microsoft Docs"
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
  - "pch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "プリコンパイル済みヘッダー"
ms.assetid: 95010260-a035-4327-9d61-222016ac146c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# プロジェクトでのプリコンパイル済みヘッダーの使用
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ここまで、プリコンパイル済みヘッダーの概要として、\/Yc と \/Yu および \/Fp の各オプション、および [hdrstop](../../preprocessor/hdrstop.md) プラグマについて説明してきました。  ここでは、プロジェクトで手動プリコンパイル済みヘッダー オプションを使用する方法について説明します。サンプル メイクファイルと、それが管理するコードを最後に載せてあります。  
  
 プロジェクトで手動プリコンパイル済みヘッダー オプションを使用する別の方法については、Visual C\+\+ の既定のセットアップで作成される MFC\\SRC ディレクトリにあるメイクファイルを参照してください。  これらのメイクファイルでは、ここで説明する方法と似た方法を使用しますが、NMAKE \(Microsoft Program Maintenance Utility\) マクロをさらに活用して、ビルド プロセスをより厳密に制御します。  
  
 このセクションは、次のトピックで構成されています。  
  
-   [ビルド プロセスでの PCH ファイル](../Topic/PCH%20Files%20in%20the%20Build%20Process.md)  
  
-   [PCH のサンプル メイクファイル](../../build/reference/sample-makefile-for-pch.md)  
  
-   [PCH のサンプル コード](../../build/reference/example-code-for-pch.md)  
  
## 参照  
 [プリコンパイル済みヘッダー ファイルの作成](../../build/reference/creating-precompiled-header-files.md)