---
title: "コンパイラの警告 (レベル 2) C4653 | Microsoft Docs"
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
  - "C4653"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4653"
ms.assetid: 90ec3317-3d39-4b4c-bcd1-97e7c799e1b6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 2) C4653
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンパイラ オプション 'option' はプリコンパイル済みヘッダーのものと一致しません。現在のオプションを優先しプリコンパイルのオプションは無視されます。  
  
 プリコンパイル済みファイルを使用するオプション \([\/Yu](../../build/reference/yu-use-precompiled-header-file.md)\) と共に指定されたオプションが、プリコンパイル済みヘッダーが作成されたときに指定されたものと一致しません。  プリコンパイル済みヘッダーが作成されたときに指定されたオプションが使用されます。  
  
 この警告は、構造体メンバーのパックの方法を指定するオプション \([\/Zp](../Topic/-Zp%20\(Struct%20Member%20Alignment\).md)\) で指定された値が、プリコンパイル済みヘッダーがコンパイルされたときに指定されたものと異なっているときに発生します。