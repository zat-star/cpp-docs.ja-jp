---
title: "Windows ストア アプリ、Windows ランタイム、および C ランタイム | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 356d6d8d-76ee-4181-9ad0-6f24b2fede38
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b332e392db2ca788d041cb73e73cf42cce85906c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="windows-store-apps-the-windows-runtime-and-the-c-run-time"></a>Windows ストア アプリ、Windows ランタイム、および C ランタイム
[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリは、[!INCLUDE[win8](../build/reference/includes/win8_md.md)] の Windows ランタイムで実行されるプログラムです。  Windows ランタイムは、[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリで使用できる関数、変数、リソースを制御する信頼できる環境です。 ただし、Windows ランタイムの仕様による制限のため、ほとんどの C ランタイム ライブラリ (CRT) 機能は [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリでは使用できません。  
  
 Windows ランタイムは次の CRT 機能をサポートしていません。  
  
-   サポートされない機能に関連したほとんどの CRT 関数。  
  
     たとえば、[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリでは、`exec` および `spawn` ファミリのルーチンを使用してプロセスを作成することはできません。  
  
     ある CRT 関数が [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリでサポートされていない場合、そのことが参照資料に記載されています。  
  
-   ほとんどのマルチバイト文字関数およびマルチバイト文字列関数。  
  
     ただし、Unicode と ANSI の両方のテキストはサポートされています。  
  
-   コンソール アプリとコマンド ライン引数。  
  
     ただし、従来のデスクトップ アプリではコンソールとコマンド ライン引数がサポートされます。  
  
-   環境変数。  
  
-   現在の作業ディレクトリという概念。  
  
-   [/MT](../build/reference/md-mt-ld-use-run-time-library.md) または `/MTd` コンパイラ オプションを使用して CRT に静的にリンクされて作成された [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリおよび DLL。  
  
     マルチスレッドおよび静的バージョンの CRT を使用するアプリがこれに当たります。  
  
-   [/MDd](../build/reference/md-mt-ld-use-run-time-library.md) コンパイラ オプションを使用して作成されたアプリ。  
  
     デバッグ、マルチスレッド、および DLL 対応バージョンの CRT を使用するアプリがこれに当たります。 このようなアプリは [!INCLUDE[win8_appstore_long](../build/reference/includes/win8_appstore_long_md.md)] ではサポートされません。  
  
 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリで使用できない CRT 関数と使用できる代替関数の詳細な一覧については、[/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)に関する記事をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [互換性](../c-runtime-library/compatibility.md)   
 [Windows ランタイムのサポートされていない CRT 関数](../c-runtime-library/windows-runtime-unsupported-crt-functions.md)   
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)