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
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 6bffc721ac685be91531b3d876234de8be2477c4
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

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
  
## <a name="see-also"></a>関連項目  
 [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)
