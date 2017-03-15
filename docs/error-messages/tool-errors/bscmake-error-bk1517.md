---
title: "BSCMAKE エラー BK1517 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "BK1517"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1517"
ms.assetid: 24391f42-0a3e-40a9-9991-c8b9a6a7b1c7
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# BSCMAKE エラー BK1517
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

sbrfile のソースファイルが \/Yc と \/Yu の両方でコンパイルされています。  
  
 .sbr ファイルは自分自身を参照しています。  このファイルは、\/Yc オプションでコンパイルされてから \/Yu オプションで再コンパイルされた可能性があります。  ソース ファイルのコンパイラ オプションを \/Yc にリセットしてから、\[リビルド\] を選択して新しい .sbr ファイルを生成します。  この後、同じソース ファイルを \/Yu オプションで再コンパイルしないでください。