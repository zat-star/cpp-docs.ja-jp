---
title: "プリプロセッサの文法 | Microsoft Docs"
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
  - "文法, プリプロセッサ"
  - "プリプロセッサ"
  - "プリプロセッサ, 文法"
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# プリプロセッサの文法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\#define**  *identifier* *token\-string*opt  
  
 *\#* **define**  *identifier*\[**\(** *identifier*opt**,** *...* **,** *identifier*opt **\)**\] *token\-string*opt  
  
 **defined\(**  *identifier* **\)**  
  
 **defined**  *identifier*  
  
 `#include` **"***path\-spec***"**  
  
 `#include` **\<***path\-spec***\>**  
  
 **\#line**  *digit\-sequence*  **"** *filename* **"** opt  
  
 *\#* **undef**  *identifier*  
  
 **\#error**  *token\-string*  
  
 **\#pragma**  *token\-string*  
  
 *conditional*:  
 *if\-part elif\-parts* opt *else\-part*opt *endif\-line*  
  
 *if\-part* :  
 *if\-linetext*  
  
 *if\-line*:  
 **\#if**  *constant\-expression*  
  
 **\#ifdef**  *identifier*  
  
 **\#ifndef**  *identifier*  
  
 *elif\-parts* :  
 *elif\-line text*  
  
 *elif\-parts elif\-line text*  
  
 *elif\-line* :  
 **\#elif**  *constant\-expression*  
  
 *else\-part* :  
 *else\-linetext*  
  
 *else\-line* :  
 `#else`  
  
 *endif\-line* :  
 `#endif`  
  
 *digit\-sequence*:  
 *digit*  
  
 *digit\-sequence digit*  
  
 *digit*: 次のいずれか  
 **0 1 2 3 4 5 6 7 8 9**  
  
 *token\-string*:  
 トークンの文字列  
  
 *token*:  
 *keyword*  
  
 *identifier*  
  
 *constant*  
  
 *operator*  
  
 `punctuator`  
  
 *filename*:  
 有効なオペレーティング システム ファイル名  
  
 *path\-spec*:  
 有効なファイル パス  
  
 *text*:  
 テキストの任意のシーケンス  
  
> [!NOTE]
>  `constant`、`constant`\-*expression*、*identifier*、*keyword*、`operator`、`punctuator` の各非終端要素については、『*C\+\+ 言語リファレンス*』の付録 A「[文法概要](../misc/grammar-summary-cpp.md)」で詳述します。  
  
## 参照  
 [文法の概要](../preprocessor/grammar-summary-c-cpp.md)