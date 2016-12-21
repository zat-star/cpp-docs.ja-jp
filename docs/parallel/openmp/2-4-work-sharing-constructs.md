---
title: "2.4 Work-sharing Constructs | Microsoft Docs"
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
ms.assetid: 25bb4ded-8466-4daa-a863-766b5a99b995
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.4 Work-sharing Constructs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

作業共有の構造は発生はチームのメンバー間の関連するステートメントの実行を配布します。  作業共有のディレクティブは新しいスレッドを開始しエントリに暗黙的なバリアは作業共有の構造はありません。  
  
 一つの作業  **バリア**  共有の構造とディレクティブのシーケンスはチームのすべてのスレッドで同じである必要があります。  
  
 OpenMP は次の作業共有の構造を定義し後の " " で説明しています :  
  
-   **For** のディレクティブ  
  
-   **セクション**  のディレクティブ  
  
-   **シングル**  のディレクティブ