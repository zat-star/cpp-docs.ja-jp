---
title: "プリプロセッサ演算子 | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "演算子 [C++], プリプロセッサ"
  - "プリプロセッサ演算子"
ms.assetid: 884126d1-0ce2-48b6-9e06-8a2d7c4a9656
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# プリプロセッサ演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

4 つのプリプロセッサ固有の演算子は、`#define` ディレクティブのコンテキストで使用されます \(各演算子の概要については、次の一覧を参照\)。  文字列化、文字定数化、およびトークン連結演算子については、次の 3 つのセクションで説明します。  **defined** 演算子の詳細については、「[\#if、\#elif、\#else、および \#endif ディレクティブ](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)」を参照してください。  
  
|演算子|動作|  
|---------|--------|  
|[文字列化演算子 \(\#\)](../preprocessor/stringizing-operator-hash.md)|対応する実引数が二重引用符で囲まれます|  
|[文字定数化演算子 \(\#@\)](../preprocessor/charizing-operator-hash-at.md)|対応する引数が単一引用符で囲まれ、文字として処理されます \(Microsoft 固有の仕様\)|  
|[トークン連結演算子 \(\#\#\)](../preprocessor/token-pasting-operator-hash-hash.md)|実引数として使用されるトークンが、他のトークンを形成するために連結されることを許可します|  
|[defined 演算子](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|特定のマクロ ディレクティブで複合式の記述を簡略化します|  
  
## 参照  
 [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)   
 [定義済みマクロ](../preprocessor/predefined-macros.md)   
 [C\/C\+\+ プリプロセッサ リファレンス](../preprocessor/c-cpp-preprocessor-reference.md)