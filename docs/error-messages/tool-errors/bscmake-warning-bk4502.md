---
title: "BSCMAKE の警告 BK4502 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "BK4502"
  - "BK1513"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1513"
  - "BK4502"
ms.assetid: ee412ec8-df03-4cdb-91ee-5d609ded8691
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# BSCMAKE の警告 BK4502
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

切り捨てられた .SBR ファイル 'filename' は、filename 内にありません。  
  
 .bsc ファイルの構成要素ではない、長さ 0 の .sbr ファイルが、更新時に指定されました。  
  
### 次のような原因をチェックして問題を解決するには  
  
1.  指定したファイル名が間違っています。  
  
2.  ファイルが削除されています。エラー [BK1513](../../error-messages/tool-errors/bscmake-error-bk1513.md) が発生します。  
  
3.  ファイルが破損しています。BSCMAKE で最初からビルドし直す必要があります。