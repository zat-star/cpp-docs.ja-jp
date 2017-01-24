---
title: "コンパイラ エラー C3552 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3552"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3552"
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3552
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'typename': 遅延指定の戻り値の型に 'auto' を含めることはできません  
  
 関数の戻り値の型のプレース ホルダーとして `auto` キーワードを使用する場合は、遅延指定の戻り値の型を指定する必要があります。 ただし、別の `auto` キーワードを使用して遅延指定の戻り値の型を指定することはできません。 たとえば、次のコード フラグメントはエラー C3552 を生成します。  
  
 `auto myFunction->auto; // C3552`