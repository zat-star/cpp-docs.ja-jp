---
title: "CRT へのリンクで使用されるメソッドの利点とトレードオフ | Microsoft Docs"
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
  - "_ATL_MIN_CRT マクロ"
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRT へのリンクで使用されるメソッドの利点とトレードオフ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プロジェクトは CRT に動的と静的にリンクできます。  アウトラインの下の表は、使用するメソッドで選択利点と欠点いない。  
  
|メソッド|利点|トレードオフ|  
|----------|--------|------------|  
|CRT に静的にリンクする<br /><br /> \( **Single\-threaded**に設定**\[ランタイム ライブラリ\]** \)|CRT DLL は、イメージが実行するシステムには必要ではありません。|スタートアップ コードによって大幅についてにサイズを大きくする、イメージに追加されます。|  
|CRT に動的にリンクする<br /><br /> \( **\[マルチスレッド\]**に設定**\[ランタイム ライブラリ\]** \)|は、イメージは CRT スタートアップ コードを必要としないため、とても小さいです。|CRT DLL は、イメージを実行するシステムである必要があります。|  
  
 トピック [ATL プロジェクトの CRT へのリンク](../atl/linking-to-the-crt-in-your-atl-project.md) は CRT にリンクする方法を選択する方法について説明します。  
  
## 参照  
 [ATL および C ランタイム コードによるプログラミング](../atl/programming-with-atl-and-c-run-time-code.md)   
 [ランタイム ライブラリの動作](../build/run-time-library-behavior.md)   
 [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)