---
title: "リソース コンパイラの致命的なエラー RC1022 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC1022"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1022"
ms.assetid: 30a0f3c7-08a8-4c40-b0de-46ee5feb789d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# リソース コンパイラの致命的なエラー RC1022
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

expected '\#endif'  
  
 `#if`、**\#ifdef**、**\#ifndef** ディレクティブを終了する `#endif` ディレクティブがありません。  
  
 このステートメントは、必ず `#if`、**\#ifdef**、**\#ifndef** のいずれかのステートメントの後ろのまだ条件判断が有効な部分に置いてください。