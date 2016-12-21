---
title: "コンパイラ エラー C2307 | Microsoft Docs"
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
  - "C2307"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2307"
ms.assetid: ce6c8033-a673-4679-9883-bedec36ae385
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2307
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

インクリメンタル コンパイルが有効になっている場合、プラグマ pragma は関数の外に指定する必要があります。  
  
 インクリメンタル コンパイルを使うときは、`data_seg` プラグマを関数ごとに指定する必要があります。