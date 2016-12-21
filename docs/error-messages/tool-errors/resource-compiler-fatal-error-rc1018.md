---
title: "リソース コンパイラの致命的なエラー RC1018 | Microsoft Docs"
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
  - "RC1018"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1018"
ms.assetid: bb1d2efd-6898-412f-bb03-9ff94c54e4dc
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リソース コンパイラの致命的なエラー RC1018
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

unexpected '\#elif'  
  
 `#elif` ディレクティブが、`#if`、**\#ifdef**、**\#ifndef** のいずれかの構造の中に置かれていません。  
  
 このステートメントは、必ず `#if`、**\#ifdef**、**\#ifndef** のいずれかのステートメントの後ろのまだ条件判断が有効な部分に置いてください。