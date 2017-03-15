---
title: "コマンド マクロとオプション マクロ | Microsoft Docs"
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
  - "コマンド マクロ (NMAKE の)"
  - "マクロ, コマンド マクロ"
  - "マクロ, オプション マクロ"
  - "オプション マクロ"
ms.assetid: 50dff03c-0dc3-4a8a-9a17-57e0e4ea9bac
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コマンド マクロとオプション マクロ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コマンド マクロは、Microsoft 製品に組み込まれています。  オプション マクロは、それらの製品に対するオプションを表すもので、既定では未定義です。  これらのマクロは両方とも、組み込みの推論規則で使用され、記述ブロックまたはユーザー定義の推論規則でも使用できます。  コマンド マクロは、オプションを含め、コマンド ラインの一部またはすべてを表すように再定義できます。  オプション マクロを未定義のままにすると、null 文字列が生成されます。  
  
|Microsoft 製品|コマンド マクロ|定義|オプション マクロ|  
|------------------|--------------|--------|---------------|  
|Macro Assembler|**AS**|ml|**AFLAGS**|  
|Basic Compiler|**BC**|bc|**BFLAGS**|  
|C Compiler|**CC**|cl|**CFLAGS**|  
|C\+\+ Compiler|**CPP**|cl|**CPPFLAGS**|  
|C\+\+ Compiler|**CXX**|cl|**CXXFLAGS**|  
|Resource Compiler|**RC**|rc|**RFLAGS**|  
  
## 参照  
 [NMAKE の特殊マクロ](../build/special-nmake-macros.md)