---
title: "プリプロセッサの文法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3c64c5a1855d80d5abc60d959bd68b33a380583b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="preprocessor-grammar"></a>プリプロセッサの文法
**#define***識別子**トークン文字列*オプトイン    
  
 *#***定義***識別子*[**(** *識別子*opt**、** *.* **、** *識別子*opt **)**]*トークン文字列*オプトイン    
  
 **定義 (***識別子* **)**   
  
 **定義されている***識別子*   
  
 `#include`**"***パス spec***"**  
  
 `#include` **\<** *パス仕様***>**  
  
 **#line***桁シーケンス***"** *filename* **"**オプトイン      
  
 *#***undef***識別子*   
  
 **#error***トークン文字列*   
  
 **#pragma***トークン文字列*   
  
 *条件付き*:  
 *if 部分 elif パーツ*opt*else 部分*opt*endif 行*  
  
 *if 部分*:  
 *if linetext*  
  
 *if 行*:  
 **#if***定数式*   
  
 **#ifdef***識別子*   
  
 **#ifndef***識別子*   
  
 *elif パーツ*:  
 *elif 行のテキスト*  
  
 *elif パーツ elif 行テキスト*  
  
 *elif 行*:  
 **#elif***定数式*   
  
 *他の部分から成る*:  
 *else linetext*  
  
 *else 行*:  
 `#else`  
  
 *endif 行*:  
 `#endif`  
  
 *桁シーケンス*:  
 *digit*  
  
 *digit-sequence digit*  
  
 *桁*: のいずれか  
 **0 1 2 3 4 5 6 7 8 9**  
  
 *トークン文字列*:  
 トークンの文字列  
  
 *トークン*:  
 *keyword*  
  
 *identifier*  
  
 *constant*  
  
 *operator*  
  
 `punctuator`  
  
 *filename* :  
 有効なオペレーティング システム ファイル名  
  
 *パス spec* :  
 有効なファイル パス  
  
 *テキスト*:  
 テキストの任意のシーケンス  
  
> [!NOTE]
>  次の非終端はでは展開、[構文規則](../cpp/lexical-conventions.md)のセクションで、 *C++ 言語リファレンス*: `constant`、 `constant` -*式*、*識別子*、*キーワード*、 `operator`、および`punctuator`です。  
  
## <a name="see-also"></a>関連項目  
 [文法の概要 (C/C++)](../preprocessor/grammar-summary-c-cpp.md)