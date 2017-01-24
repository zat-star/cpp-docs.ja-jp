---
title: "リンカ ツール エラー LNK1200 | Microsoft Docs"
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
  - "LNK1200"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1200"
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカ ツール エラー LNK1200
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プログラム データベース 'filename' を読み取れません。  
  
 プログラム データベース \(PDB\) を読み込むことができません。  
  
 このエラーは、ファイルの破損が原因で発生する場合があります。  
  
 `filename` がオブジェクト ファイルの PDB の場合は、[\/Zi](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md) オプションを使用して、そのオブジェクト ファイルを再コンパイルしてください。  
  
 `filename` がメイン出力ファイルのプログラム データベースで、インクリメンタル リンクでエラーが発生した場合は、プログラム データベースを削除し、再リンクしてください。