---
title: "Tools.ini と NMAKE | Microsoft Docs"
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
  - "NMAKE プログラム, 読み取り (ファイルを)"
  - "Tools.ini および NMake"
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Tools.ini と NMAKE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\/R が指定されない限り、NMAKE は、メイクファイルを読み取る前に Tools.ini を読み取ります。  Tools.ini は、最初は現在のディレクトリで検索され、次に INIT 環境変数で指定されたディレクトリで検索されます。  初期化ファイルの NMAKE 設定のセクションは、`[NMAKE]` で始まり、すべてのメイクファイル情報を格納できます。  コメントは、シャープ記号 \(\#\) で始まる独立した行で示します。  
  
## 参照  
 [NMAKE の実行](../build/running-nmake.md)