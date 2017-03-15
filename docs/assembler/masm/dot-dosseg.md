---
title: ".DOSSEG | Microsoft Docs"
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
  - ".DOSSEG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".DOSSEG directive"
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .DOSSEG
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MS\-DOS のセグメントの規則に従ってセグメントと Orders: 最初にコード。次に DGROUP の DGROUP とセグメントに分割します。  
  
## 構文  
  
```  
  
.DOSSEG  
  
```  
  
## 解説  
 DGROUP の部分はこの順序に従います : BSS またはスタックBSS セグメントと最終的にスタック セグメントのセグメントありません。  MASM に依存しない型プログラムの CodeView のサポートを確認するには主に使用します。  [DOSSEG](../../assembler/masm/dosseg.md) と同じです。  
  
## 参照  
 [Directives Reference](../../assembler/masm/directives-reference.md)