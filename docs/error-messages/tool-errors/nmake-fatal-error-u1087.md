---
title: "NMAKE の致命的なエラー U1087 | Microsoft Docs"
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
  - "U1087"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1087"
ms.assetid: 5236ab54-e117-484d-99c3-852b061fd3d0
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE の致命的なエラー U1087
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

同じターゲットに : と :: の依存ファイルを持てません。  
  
 1 つのターゲットを単独のコロン \(**:**\) の依存関係行と二重コロン \(`::`\) の依存関係行の両方で指定することはできません。  
  
 1 つのターゲットを複数の記述ブロックで指定する場合は、各依存関係行で `::` を使用してください。