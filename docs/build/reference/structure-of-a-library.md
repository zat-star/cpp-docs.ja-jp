---
title: "ライブラリの構造 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ライブラリ, 構造体"
ms.assetid: a5fda8e8-4a1b-4499-9095-0df935262ce4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# ライブラリの構造
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ライブラリは、COFF オブジェクトで構成されます。  ライブラリ内のオブジェクトの関数とデータは、プログラム内のほかのオブジェクト、つまり外部から参照できます。  ライブラリ内のオブジェクトは、ライブラリ メンバーとも呼ばれます。  
  
 ライブラリの内容に関する詳細情報が必要な場合は、DUMPBIN を \/LINKERMEMBER オプションで実行します。  詳細については、「[DUMPBIN リファレンス](../../build/reference/dumpbin-reference.md)」を参照してください。  
  
## 参照  
 [LIB の概要](../../build/reference/overview-of-lib.md)