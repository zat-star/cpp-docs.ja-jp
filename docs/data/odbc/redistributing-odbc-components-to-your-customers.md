---
title: "ODBC の構成要素の配布 | Microsoft Docs"
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
  - "コンポーネント [C++]"
  - "コンポーネント [C++], 配布"
  - "コンポーネント [C++], 再配布"
  - "ODBC データ ソース アドミニストレーター"
  - "ODBC コンポーネント, 再配布"
  - "ODBC, 配布 (コンポーネントを)"
ms.assetid: 17b065b4-a307-4b89-99ac-d05831cfab87
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ODBC の構成要素の配布
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ODBC データ ソース アドミニストレーターの機能をアプリケーションに取り込んだ場合は、これらのプログラムを実行するために必要なファイルも頒布する必要があります。  必要なファイルは、Visual C\+\+ の CD\-ROM の \\OS\\System フォルダーにあります。  同じフォルダーにある Redistrb.wri ファイルと使用許諾契約書の両方に、再頒布できる ODBC ファイルの一覧があります。  
  
 ODBC ドライバーをアプリケーションに同梱する場合は、必ずこのファイルまたはライセンス確認書を調べてください。  DLL などのファイルについても、どのファイルをユーザーに送るかを調べる必要があります。  
  
 ODBC コンポーネントと ODBC ドライバーについては、「[データベース サポートのインストール](../../data/installing-database-support-mfc-atl.md)」を参照してください。また、ActiveX コントロールの再頒布方法については、「[コントロールを再配布する](../Topic/Redistributing%20Controls.md)」を参照してください。  
  
 ほとんどの場合は、ODBC カーソル ライブラリ用の ODBCCR32.DLL というファイルの頒布も必要です。  Odbccr32.dll は ODBC カーソル ライブラリです。  このライブラリは、レベル 1 ドライバーに前方および後方のスクロール機能を提供します。  また、スナップショットのサポートに必要な機能も提供します。  ODBC カーソル ライブラリの詳細については、「[ODBC : ODBC カーソル ライブラリ](../../data/odbc/odbc-the-odbc-cursor-library.md)」を参照してください。  
  
 ODBC をデータベース クラスと一緒に使用する方法の詳細については、次のトピックを参照してください。  
  
-   [ODBC : ODBC カーソル ライブラリ](../../data/odbc/odbc-the-odbc-cursor-library.md)  
  
-   [ODBC : ODBC データ ソースの設定](../../data/odbc/odbc-configuring-an-odbc-data-source.md)  
  
-   [ODBC : ODBC API 関数の直接呼び出し](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)  
  
## 参照  
 [ODBC の基礎](../../data/odbc/odbc-basics.md)   
 [ODBC データ ソース アドミニストレーター](../../data/odbc/odbc-administrator.md)