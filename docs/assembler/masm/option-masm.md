---
title: "OPTION (MASM) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "option"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OPTION directive"
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# OPTION (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アセンブラーの有効と無効の機能。  
  
## 構文  
  
```  
  
OPTION   
optionlist  
  
```  
  
## 解説  
 使用できるオプションは次のとおりです。:  
  
|||||  
|-|-|-|-|  
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**エミュレーター**|  
|**NOEMULATOR**|**エピローグ**|**EXPR16**|**EXPR32**|  
|**言語**|**LJMP**|**NOLJMP**|**M510**|  
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**オフセット**|  
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|  
|**PROC**|**プロローグ**|**READONLY**|**NOREADONLY**|  
|**SCOPED**|**NOSCOPED**|**SEGMENT**|**SETIF2**。|  
  
 言語の構文は 15 *x は*  CSYSCALLSTDCALLPascalFortran基本の 1 つです。 **言語のオプション :** に*X* です。  SYSCALLPascalFortran および基本の [.MODEL](../../assembler/masm/dot-model.md) はフラットで使用されるでサポートされません。  
  
## 参照  
 [Directives Reference](../../assembler/masm/directives-reference.md)