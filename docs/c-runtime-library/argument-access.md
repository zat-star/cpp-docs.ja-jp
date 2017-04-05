---
title: "引数へのアクセス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.arguments
dev_langs:
- C++
helpviewer_keywords:
- argument access macros [C++]
- variable-length argument lists
ms.assetid: 7046ae34-a0ec-44f0-815d-3209492a3e19
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 66f9ff6dff86bbdff2ec86970a4176f3581316fa
ms.lasthandoff: 03/29/2017

---
# <a name="argument-access"></a>引数へのアクセス
`va_arg`、`va_end`、`va_start` の各マクロは、引数の数が可変である場合に、関数の引数へのアクセスを提供します。 これらのマクロは、ANSI C 互換の場合は STDARG.H で、UNIX System V と互換性がある場合は VARARGS.H で定義されています。  
  
### <a name="argument-access-macros"></a>引数アクセス マクロ  
  
|マクロ|用途|  
|-----------|-------------------------------|  
|[va_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|リストから引数を取得します|  
|[va_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|ポインターをリセットします|  
|[va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|引数リストの先頭にポインターを設定します|  
  
## <a name="see-also"></a>関連項目  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)
