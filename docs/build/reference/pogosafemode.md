---
title: "PogoSafeMode | Microsoft Docs"
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
  - "PogoSafeMode"
ms.assetid: 2daeeff7-44cb-417f-90eb-6b9edf658533
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# PogoSafeMode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アプリケーションのプロファイリングに高速モードとセーフ モードのどちらを使用するかを指定します。  
  
## 構文  
  
```  
PogoSafeMode  
```  
  
## 解説  
 ガイド付き最適化のプロファイル \(PGO: Profile\-Guided Optimization\) では、プロファイリング フェーズで高速モードとセーフ モードの 2 つのモードを使用できます。  高速モードでプロファイリングを行う場合は、**INC** 命令を使用してデータ カウンター数を増やします。  **INC** 命令は高速ですが、スレッド セーフではありません。  セーフ モードでプロファイリングを行う場合は、**LOCK INC** 命令を使用してデータ カウンター数を増やします。  **LOCK INC** 命令は **INC** 命令と同じ機能を持ち、スレッド セーフですが、**INC** 命令より低速です。  
  
 既定では、PGO プロファイリングは高速モードで動作します。  `PogoSafeMode` は、セーフ モードを使用する場合にのみ必要です。  
  
 PGO プロファイリングをセーフ モードで実行するには、システムに応じて、環境変数 `PogoSafeMode` かリンカー スイッチ **\-PogoSafeMode** のどちらかを使用する必要があります。  x64 コンピューターでプロファイリングを実行する場合は、リンカー スイッチを使用する必要があります。  x86 コンピューターでプロファイリングを実行する場合は、最適化処理を開始する前に、環境変数を任意の値に定義する必要があります。  
  
## 使用例  
  
```  
set PogoSafeMode=1  
```  
  
## 参照  
 [ガイド付き最適化のプロファイルの環境変数](../../build/reference/environment-variables-for-profile-guided-optimizations.md)   
 [ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)