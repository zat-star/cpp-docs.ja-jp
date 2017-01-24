---
title: "リソース コンパイラの致命的なエラー RC1019 | Microsoft Docs"
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
  - "RC1019"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1019"
ms.assetid: 432fff44-04a9-4e13-91c6-870df6f0b4e4
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リソース コンパイラの致命的なエラー RC1019
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

unexpected '\#else'  
  
 `#else` ディレクティブが、`#if`、**\#ifdef**、**\#ifndef** のいずれかの構造の中に置かれていません。  
  
 このステートメントは、必ず `#if`、**\#ifdef**、**\#ifndef** のいずれかのステートメントの後ろのまだ条件判断が有効な部分に置いてください。