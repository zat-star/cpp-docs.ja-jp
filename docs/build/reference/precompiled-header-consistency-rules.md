---
title: "プリコンパイル済みヘッダーの一貫性規則 | Microsoft Docs"
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
  - "プリコンパイル済みヘッダー ファイル, 一貫性規則"
ms.assetid: 844b1a14-5b0b-4276-a1f5-cc62f13f6dda
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# プリコンパイル済みヘッダーの一貫性規則
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ここでは、プリコンパイル済みヘッダーをより効率的に使用するためのガイドラインを示します。  
  
-   [PCH ファイルの使用時の一貫性規則](../../build/reference/consistency-rules-for-per-file-use-of-precompiled-headers.md)  
  
-   [\/Yc および \/Yu の一貫性規則](../../build/reference/consistency-rules-for-yc-and-yu.md)  
  
 PCH ファイルは、マシン環境についての情報およびプログラムのメモリ アドレス情報を含んでいるので、それを作成したマシン上だけで使用してください。  
  
## 参照  
 [プリコンパイル済みヘッダー ファイルの作成](../../build/reference/creating-precompiled-header-files.md)