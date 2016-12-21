---
title: "リンカー入力としての .ilk ファイル | Microsoft Docs"
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
  - ".ilk ファイル"
  - "ILK ファイル"
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカー入力としての .ilk ファイル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

インクリメンタル リンクを行うと、最初のインクリメンタル リンクで作成されたステータス ファイル \(.ilk ファイル\) が更新されます。  このファイルのベース名は .exe ファイルまたは .dll ファイルと同じであり、拡張子は .ilk です。  以降のインクリメンタル リンクによって、そのつど .ilk ファイルが更新されます。  .ilk ファイルがない場合、LINK ではフル リンクを行って .ilk ファイルを新しく作成します。  .ilk ファイルが使用できない場合は、ノンインクリメンタル リンクを行います。  インクリメンタル リンクの詳細については、[\/INCREMENTAL \(インクリメンタル リンクを行う\)](../../build/reference/incremental-link-incrementally.md) オプションに関するトピックを参照してください。  
  
## 参照  
 [LINK の入力ファイル](../../build/reference/link-input-files.md)   
 [リンカー オプション](../../build/reference/linker-options.md)