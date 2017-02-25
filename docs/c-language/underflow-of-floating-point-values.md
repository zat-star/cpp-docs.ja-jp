---
title: "浮動小数点値のアンダーフロー | Microsoft Docs"
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
ms.assetid: 78af8016-643c-47db-b4f1-7f06cb4b243e
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 浮動小数点値のアンダーフロー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.5.1** 数値演算関数がアンダーフロー エラー時に、整数式 `errno` を `ERANGE` マクロの値に設定するかどうか  
  
 浮動小数点アンダーフローは、式 `errno` を `ERANGE` に設定しません。  値がゼロに近づき、最終的にアンダーフローすると、値はゼロに設定されます。  
  
## 参照  
 [ライブラリ関数](../c-language/library-functions.md)