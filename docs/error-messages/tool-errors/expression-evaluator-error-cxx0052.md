---
title: "式エバリュエーター エラー CXX0052 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0052"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0052"
  - "CXX0052"
ms.assetid: 5060d479-d0a4-4682-b858-c8b9a4f324e6
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 式エバリュエーター エラー CXX0052
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

メンバー関数がありません  
  
 ブレークポイントとして指定されたメンバー関数が見つかりません。  インライン展開された関数にブレークポイントを設定すると、このエラーが発生する場合があります。  
  
 インライン関数に対してブレークポイントを設定するときは、インライン関数の強制解除オプション \(\/OB0\) を指定してコンパイルしてください。  
  
 定義されていない関数を呼び出している可能性もあります。  
  
 このエラーは CAN0052 と同じものです。