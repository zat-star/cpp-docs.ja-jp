---
title: "C ランタイム エラー R6028 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6028"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6028"
ms.assetid: 81e99079-4388-4244-a4f7-4641c508871c
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# C ランタイム エラー R6028
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ヒープを初期化できません。  
  
 このエラーは、オペレーティング システムでアプリケーションのメモリ プールを作成できなかった場合に発生します。  具体的には、C ランタイム \(CRT\) が `HeapCreate` という Win32 関数を呼び出し、失敗したことを示す NULL が返されます。  
  
 アプリケーションの起動中にこのエラーが発生した場合は、欠陥があるドライバーが読み込まれているため、システムでヒープ要求を満たすことができない可能性があります。  Windows Update またはハードウェアのベンダーの Web サイトで、更新されたドライバーがないかどうかを確認してください。