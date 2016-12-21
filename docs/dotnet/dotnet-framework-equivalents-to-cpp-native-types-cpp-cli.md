---
title: "C++ ネイティブ型と等価な .NET Framework ネイティブ型 (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".NET Framework [C++], C++ と等価"
ms.assetid: 7f116a9a-26cd-46db-9877-a63ffdc88723
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ ネイティブ型と等価な .NET Framework ネイティブ型 (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ の組み込み型のキーワードは、次のとおりです。これらは、**System** 名前空間に組み込まれた型のエイリアスです。  
  
|Visual C\+\+ 型|.NET Framework 型|  
|--------------------|----------------------|  
|**bool**|**System.Boolean**|  
|**signed char** \(詳細については、[\/J](../build/reference/j-default-char-type-is-unsigned.md) を参照してください\)|**System.SByte**|  
|**unsigned char**|**System.Byte**|  
|**wchar\_t**|**System.Char**|  
|**double**、**long double**|**System.Double**|  
|**float**|**System.Single**|  
|**int**、**signed int**、**long**、**signed long**|**System.Int32**|  
|**unsigned int**、**unsigned long**|**System.UInt32**|  
|**\_\_int64**、**signed \_\_int64**|**System.Int64**|  
|**unsigned \_\_int64**|**System.UInt64**|  
|**short**、**signed short**|**System.Int16**|  
|**unsigned short**|**System.UInt16**|  
|**void**|**System.Void**|  
  
## 参照  
 [マネージ型](../Topic/Managed%20Types%20\(C++-CLI\).md)