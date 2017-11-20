---
title: "引数へのアクセス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.arguments
dev_langs: C++
helpviewer_keywords:
- argument access macros [C++]
- variable-length argument lists
ms.assetid: 7046ae34-a0ec-44f0-815d-3209492a3e19
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c216c009d84771fdf34426b6121a89eb4b3f73e4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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