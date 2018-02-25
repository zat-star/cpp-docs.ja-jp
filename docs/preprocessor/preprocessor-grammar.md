---
title: "プリプロセッサの文法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 02b3597b035e3ea4bfa1670aa405109f4c01a077
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="preprocessor-grammar"></a>プリプロセッサの文法
**#define**  *identifier* *token-string*opt  
  
 *#* **define**  *identifier*[**(** *identifier*opt**,** *...* **,** *identifier*opt **)**] *token-string*opt  
  
 **defined(**  *identifier* **)**  
  
 **defined**  *identifier*  
  
 `#include` **"***path-spec***"**  
  
 `#include` **\<***path-spec***>**  
  
 **#line**  *digit-sequence*  **"** *filename* **"**opt  
  
 *#* **undef**  *identifier*  
  
 **#error**  *token-string*  
  
 **#pragma**  *token-string*  
  
 *条件付き*:  
 *if 部分 elif パーツ*opt*else 部分*opt*endif 行*  
  
 *if-part* :  
 *if-linetext*  
  
 *if 行*:  
 **#if**  *constant-expression*  
  
 **#ifdef**  *identifier*  
  
 **#ifndef**  *identifier*  
  
 *elif-parts* :  
 *elif 行のテキスト*  
  
 *elif パーツ elif 行テキスト*  
  
 *elif 行*:  
 **#elif**  *constant-expression*  
  
 *else-part* :  
 *else-linetext*  
  
 *else 行*:  
 `#else`  
  
 *endif 行*:  
 `#endif`  
  
 *digit-sequence* :  
 *digit*  
  
 *digit-sequence digit*  
  
 *桁*: のいずれか  
 **0 1 2 3 4 5 6 7 8 9**  
  
 *token-string* :  
 トークンの文字列  
  
 *トークン*:  
 *keyword*  
  
 *identifier*  
  
 *constant*  
  
 *operator*  
  
 `punctuator`  
  
 *filename* :  
 有効なオペレーティング システム ファイル名  
  
 *path-spec* :  
 有効なファイル パス  
  
 *テキスト*:  
 テキストの任意のシーケンス  
  
> [!NOTE]
>  次の非終端はでは展開、[構文規則](../cpp/lexical-conventions.md)のセクションで、 *C++ 言語リファレンス*: `constant`、 `constant` -*式*、*識別子*、*キーワード*、 `operator`、および`punctuator`です。  
  
## <a name="see-also"></a>参照  
 [文法の概要 (C/C++)](../preprocessor/grammar-summary-c-cpp.md)