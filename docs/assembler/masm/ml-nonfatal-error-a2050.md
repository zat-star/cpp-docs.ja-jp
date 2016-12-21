---
title: "ML Nonfatal Error A2050 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2050"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2050"
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ML Nonfatal Error A2050
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**real BCD の数が示されます。**  
  
 浮動小数点 \(real\) の数または 2 進化 10 進数の \(BCD\) 定数はデータの初期化子としては使用されていません。  
  
 発生する以下のいずれかの操作 :  
  
-   実数か BCD は式で使用されています。  
  
-   実数は [ダブルワード](../../assembler/masm/dword.md)[QWORD](../../assembler/masm/qword.md)または [TBYTE](../../assembler/masm/tbyte.md) 以外のディレクティブを初期化するために使用されています。  
  
-   BCD が `TBYTE` 以外のディレクティブを初期化するために使用されています。  
  
## 参照  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)