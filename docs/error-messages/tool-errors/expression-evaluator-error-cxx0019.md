---
title: "式エバリュエーター エラー CXX0019 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0019"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0019"
  - "CXX0019"
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 式エバリュエーター エラー CXX0019
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

タイプキャストが無効です  
  
 型キャストが処理できません。  
  
 このエラーは CAN0019 と同じものです。  
  
### 次のような原因をチェックして問題を解決するには  
  
1.  未知の型が指定されています。  
  
2.  ポインター型のレベルが深すぎます。  たとえば、次の型キャスト  
  
    ```  
    (char **)h_message  
    ```  
  
     は、C の式エバリュエーターでは評価できません。