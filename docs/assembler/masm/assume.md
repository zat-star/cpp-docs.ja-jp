---
title: "ASSUME | Microsoft Docs"
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
  - "ASSUME"
  - "_assume_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ASSUME directive"
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ASSUME
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

レジスタ値のエラー チェックを有効にします。  
  
## 構文  
  
```  
  
      ASSUME segregister:name [[, segregister:name]]...  
ASSUME dataregister:type [[, dataregister:type]]...  
ASSUME register:ERROR [[, register:ERROR]]...  
ASSUME [[register:]] NOTHING [[, register:NOTHING]]...  
```  
  
## 解説  
 `ASSUME` を実行すると特定のレジスタの値の変更に対してアセンブラーを監視できます。   **エラー**  レジスタを使用するとエラーが発生します。  **Nothing** を削除するとエラー チェックを登録します。  1 種類のステートメントの前提でさまざまな種類の結合できます。  
  
## 参照  
 [Directives Reference](../../assembler/masm/directives-reference.md)