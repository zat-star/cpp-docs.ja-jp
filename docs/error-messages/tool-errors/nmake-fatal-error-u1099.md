---
title: "NMAKE の致命的なエラー U1099 | Microsoft Docs"
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
  - "U1099"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1099"
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE の致命的なエラー U1099
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

スタック オーバーフロー  
  
 処理中のメイクファイルは複雑すぎるため、NMAKE の現在のスタックに割り当てることができません。  NMAKE のスタックの大きさは 0x3000 \(12K\) です。  
  
 NMAKE のスタック割り当てを増やすには、大きな値のスタック オプションを指定して [editbin \/stack](../../build/reference/stack.md) を実行します。  
  
 **editbin \/STACK:reserve NMAKE.EXE**  
  
 上記の例で、*reserve* には NMAKE に指定された現在のスタック割り当てよりも大きい値を指定します。