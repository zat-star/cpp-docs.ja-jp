---
title: "pgosweep | Microsoft Docs"
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
  - "pgosweep プログラム"
  - "ガイド付き最適化のプロファイル, pgosweep"
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# pgosweep
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ガイド付き最適化のプロファイルで使用して、実行中のプログラムのすべてのプロファイル データを .pgc ファイルに書き込みます。  
  
## 構文  
  
```  
pgosweep [options] image pgcfile  
```  
  
#### パラメーター  
 `options`  
 省略可能なパラメーターで、空白のままにしておくことができます。  `options` に有効な値は次のようになります。  
  
-   **\/?** または **\/help** により、ヘルプ メッセージが表示されます。  
  
-   **\/noreset** は、ランタイム データ構造体にカウントを保存します。  
  
 `image`  
 コンパイラ オプション \/LTCG:PGINSTRUMENT を使用して作成された .exe または .dll ファイルのフル パス。  
  
 `pgcfile`  
 このコマンドがデータ カウントを書き出す先の .pgc ファイル。  
  
## 解説  
 このコマンドは、\/LTCG:PGINSTRUMENT コンパイラ オプションでビルドされたプログラムに有効です。  これは実行中のプログラムを中断し、プロファイル データを新しい .pgc ファイルに書き込みます。  既定で、このコマンドは書き込み操作を行うたびにカウントをリセットします。  **\/noreset** オプションを指定すると、このコマンドは値を記録しますが、実行中のプログラムで値をリセットすることはありません。  このオプションは、プロファイル データを後から取得すると、データを複製します。  
  
 `pgosweep` の 2 次的な用途として、プロファイル情報をアプリケーションのランタイムのためだけに取得するということがあります。  たとえば、アプリケーションの起動直後に `pgosweep` を実行して、そのファイルを破棄することができます。  このようにすると、スタートアップ コストに関連するプロファイル データが削除されます。  その後、アプリケーションを終了する前に `pgosweep` を実行できます。  このようにすると、収集されたデータは、ランタイムだけに取得されたプロファイル情報となります。  
  
 .pgc ファイル \(`pgcfile`\) に名前を付ける場合 *appname\!n*.pgc である標準書式を使用できます。  この形式を使用すると、コンパイラはこのデータを \/LTCG:PGO フェーズで見つけます。  標準の形式を使用しない場合は、[pgomgr](../../build/reference/pgomgr.md) を使用して、.pgc ファイルをマージする必要があります。  
  
## 使用例  
  
```  
pgosweep myapp.exe myapp!1.pgc  
```  
  
 この例では、`pgosweep` により、myapp.exe の現在のプロファイル情報がすべて myapp\!1.pgc に書き込まれます。  
  
## 参照  
 [ガイド付き最適化のプロファイル用ツール](../../build/reference/tools-for-manual-profile-guided-optimization.md)