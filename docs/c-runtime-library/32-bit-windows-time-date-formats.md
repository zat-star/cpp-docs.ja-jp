---
title: "32 ビット Windows の時刻と日付の形式 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.time"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "32 ビット Windows"
ms.assetid: ef1589db-84d7-4b24-8799-7c7a22cfe2bf
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 32 ビット Windows の時刻と日付の形式
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ファイルの時刻と日付がビット フィールドとして符号なし整数を使用して、それぞれ格納されます。  次のようファイルの時刻と日付はパック:  
  
### 時刻  
  
|ビット位置:|0   1   2   3   4|5 6 7 8 9 A|ef B C D|  
|------------|-----------------------|-----------------|--------------|  
|長さ:|5|6|5|  
|目次:|hours|minutes|2 番目の 2 インクリメント|  
|値の範囲:|0–23|0–59|2 番目のガベージ コレクションが間隔 2 の 0–29|  
  
### Date  
  
|ビット位置:|0   1   2   3   4   5   6|7 8 9 A|ef B C D|  
|------------|-------------------------------|-------------|--------------|  
|長さ:|7|4|5|  
|目次:|年|月|日|  
|値の範囲:|0–119|1–12|1–31|  
||\(1980 年に関連する\)|||  
  
## 参照  
 [グローバル定数](../c-runtime-library/global-constants.md)