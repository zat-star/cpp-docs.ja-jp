---
title: "リンカー ツールの警告 LNK4071 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4071"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4071"
ms.assetid: 803f8c34-8219-4f55-a4ae-7133ceff2ba3
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# リンカー ツールの警告 LNK4071
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

これ以降のリンクではインクリメンタル リンクを行えません。  
  
 LINK は 1 つ以上のシンボルに対して重複定義を見つけましたが、[\/FORCE](../../build/reference/force-force-file-output.md) オプションまたは **\/FORCE:MULTIPLE** オプションが使われているので、エラーの有無にかかわらず出力ファイルを作成します。  LINK はインクリメンタル ステータス ファイル \(.ilk\) を削除します。