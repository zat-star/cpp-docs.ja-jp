---
title: "NMAKE の警告 U4004 | Microsoft Docs"
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
  - "U4004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U4004"
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE の警告 U4004
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ターゲット 'targetname' に対してルールが多すぎます。  
  
 指定されたターゲットには、単独のコロン \(**:**\) を区切り記号に使用した 2 つ以上の記述ブロックが指定されています。  最初の記述ブロックにあるコマンドだけが実行され、2 つ目以降の記述ブロックは無視されます。  
  
 複数の依存関係行で 1 つのターゲットを指定するときは、それぞれの依存関係行で区切り記号として二重コロン \(`::`\) を使用してください。