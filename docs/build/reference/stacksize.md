---
title: "STACKSIZE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "STACKSIZE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STACKSIZE ステートメント (.def ファイル)"
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# STACKSIZE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

スタック サイズをバイト単位で設定します。  
  
```  
STACKSIZE reserve[,commit]  
```  
  
## 解説  
 コマンド ラインでスタック サイズを指定するには、[\/STACK \(スタック アロケーション\)](../../build/reference/stack-stack-allocations.md) オプションを使用します。  引数 *reserve* と引数 `commit` については、\/STACK の説明を参照してください。  
  
 このオプションは、DLL に対しては適用されません。  
  
## 参照  
 [モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)