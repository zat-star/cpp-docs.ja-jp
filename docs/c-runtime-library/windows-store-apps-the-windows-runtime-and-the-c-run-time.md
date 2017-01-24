---
title: "Windows ストア アプリ、Windows ランタイム、および C ランタイム | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 356d6d8d-76ee-4181-9ad0-6f24b2fede38
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Windows ストア アプリ、Windows ランタイム、および C ランタイム
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリは、[!INCLUDE[win8](../build/includes/win8_md.md)] 上で稼働する [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 内で実行されるプログラムです。  [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] は、[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリで使用できる関数、変数、およびリソースを制御する信頼できる環境です。  ただし、[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] の仕様による制限事項のため、ほとんどの C ランタイム ライブラリ \(CRT\) 機能を [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリで使用できません。  
  
 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] は、次の CRT 機能をサポートしていません。  
  
-   サポートされない機能に関連したほとんどの CRT 関数。  
  
     たとえば、[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリでは、`exec` および `spawn` ファミリのルーチンを使用してプロセスを作成することはできません。  
  
     ある CRT 関数が [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリでサポートされていない場合、そのことが参照資料に記載されています。  
  
-   ほとんどのマルチバイト文字関数およびマルチバイト文字列関数。  
  
     ただし、Unicode と ANSI の両方のテキストはサポートされています。  
  
-   コンソール アプリとコマンド ライン引数。  
  
     ただし、従来のデスクトップ アプリではコンソールとコマンド ライン引数がサポートされます。  
  
-   環境変数。  
  
-   現在の作業ディレクトリという概念。  
  
-   [\/MT](../build/reference/md-mt-ld-use-run-time-library.md) または `/MTd` コンパイラ オプションを使用して CRT に静的にリンクされて作成された [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリおよび DLL。  
  
     マルチスレッドおよび静的バージョンの CRT を使用するアプリがこれに当たります。  
  
-   [\/MDd](../build/reference/md-mt-ld-use-run-time-library.md) コンパイラ オプションを使用してビルドされたアプリ。  
  
     デバッグ、マルチスレッド、および DLL 対応バージョンの CRT を使用するアプリがこれに当たります。  このようなアプリは [!INCLUDE[win8_appstore_long](../build/reference/includes/win8_appstore_long_md.md)] ではサポートされません。  
  
 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリで使用できない CRT 関数と使用可能な代替関数の完全な一覧については「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 参照  
 [互換性](../c-runtime-library/compatibility.md)   
 [Windows ランタイムのサポートされていない CRT 関数](../Topic/Windows%20Runtime%20Unsupported%20CRT%20Functions.md)   
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)