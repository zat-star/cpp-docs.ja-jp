---
title: "型チェック (CRT) | Microsoft Docs"
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
  - "c.types"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "チェック (型を)"
  - "型チェック"
  - "可変個の引数を取る関数"
ms.assetid: 1ba7590b-d1c0-4636-b6a0-e231395abdad
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 型チェック (CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コンパイラは、可変個の引数をとる関数に対して、型チェックを限定的に行います。  
  
|関数呼び出し|型チェックされる引数|  
|------------|----------------|  
|`_cprintf_s`, `_cscanf_s`, `printf_s`, `scanf_s`|最初の引数 \(書式指定文字列\)|  
|`fprintf_s`, `fscanf_s`, `sprintf_s`, `sscanf_s`|最初の 2 つの引数 \(ファイルまたはバッファー、および書式指定文字列\)|  
|`_snprintf_s`|最初の 3 つの引数 \(ファイルまたはバッファー、カウント、および書式指定文字列\)|  
|`_open`|最初の 2 つの引数 \(パスおよび `_open` フラグ\)|  
|`_sopen_s`|最初の 3 つの引数 \(パス、`_open` フラグ、および共有モード\)|  
|`_execl`, `_execle`, `_execlp`, `_execlpe`|最初の 2 つの引数 \(パス、および最初の引数へのポインター\)|  
|`_spawnl`, `_spawnle`, `_spawnlp`, `_spawnlpe`|最初の 3 つの引数 \(モード フラグ、パス、および最初の引数へのポインター\)|  
  
 コンパイラは、これらの関数に対応するワイド文字関数についても、同様の型チェックを限定的に行います。  
  
## 参照  
 [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)