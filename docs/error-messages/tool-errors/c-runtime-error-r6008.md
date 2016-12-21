---
title: "C ランタイム エラー R6008 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6008"
ms.assetid: f0f304fc-709a-4843-bc7e-bad1ae0d1649
caps.latest.revision: 7
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C ランタイム エラー R6008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

not enough space for arguments  
  
 プログラムを読み込むことはできましたが、メモリ不足のため **argv** 配列を生成できません。  
  
### 次のような解決策を使用して問題を解決するには  
  
1.  プログラムで使えるメモリ量を増加します。  
  
2.  コマンド ライン引数の数やサイズを小さくします。  
  
3.  不要な変数を削除し、環境サイズを小さくします。