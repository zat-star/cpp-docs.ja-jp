---
title: "型チェック (CRT) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.types
dev_langs:
- C++
helpviewer_keywords:
- checking type
- variable argument functions
- type checking
ms.assetid: 1ba7590b-d1c0-4636-b6a0-e231395abdad
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d18ae0818dd839bee0d93bd7194dadcc9abf6627
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="type-checking-crt"></a>型チェック (CRT)
コンパイラは、制限付きの型チェックを行います。次のように、状況によって異なる数の引数をチェックします。  
  
|関数呼び出し|型がチェックされる引数|  
|-------------------|-----------------------------|  
|`_cprintf_s`, `_cscanf_s`, `printf_s`, `scanf_s`|最初の引数 (書式設定文字列)|  
|`fprintf_s`, `fscanf_s`, `sprintf_s`, `sscanf_s`|最初の 2 つの引数 (ファイルまたはバッファー、書式設定文字列)|  
|`_snprintf_s`|最初の 3 つの引数 (ファイルまたはバッファー、カウント、書式設定文字列)|  
|`_open`|最初の 2 つの引数 (パス、`_open` フラグ)|  
|`_sopen_s`|最初の 3 つの引数 (パス、`_open` フラグ、共有モード)|  
|`_execl`, `_execle`, `_execlp`, `_execlpe`|最初の 2 つの引数 (パス、最初の引数のポインター)|  
|`_spawnl`, `_spawnle`, `_spawnlp`, `_spawnlpe`|最初の 3 つの引数 (モード フラグ、パス、最初の引数のポインター)|  
  
 コンパイラでは、ワイド文字版のこれらの関数についても同じ制限付きの型チェックを行います。  
  
## <a name="see-also"></a>参照  
 [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)