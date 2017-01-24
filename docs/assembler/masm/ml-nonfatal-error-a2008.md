---
title: "ML Nonfatal Error A2008 | Microsoft Docs"
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
  - "A2008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2008"
ms.assetid: ca24157f-c88a-4678-ae06-3bc3cd956001
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ML Nonfatal Error A2008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**構文エラー :**  
  
 現在の場所でトークンが構文エラーを引き起こしました。  
  
 次のいずれかが発生する可能性があります :  
  
-   ドットのプレフィックスがに追加されるかまたはディレクティブから除外されました。  
  
-   予約語を識別子として **C サイズ** \(やなど\) が使用されていました。  
  
-   現在のプロセッサコプロセッサの選択では利用できなかった命令が使用されました。  
  
-   比較の実行時の関係演算子は演算子の代わりに条件付きアセンブリのステートメント \(`==` など\) が使用されていました [EQ](../../assembler/masm/operator-eq.md)\(など\)。  
  
-   命令またはディレクティブに十分なオペランドが指定されました。  
  
-   旧式のディレクティブが使用されました。  
  
## 参照  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)