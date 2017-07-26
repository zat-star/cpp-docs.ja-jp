---
title: "定数とグローバル変数のマップ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _tenviron
- _TEOF
- _tfinddata_t
dev_langs:
- C++
helpviewer_keywords:
- tfinddatat function
- tenviron function
- TEOF type
- _TEOF type
- generic-text mappings
- _tenviron function
- _tfinddata_t function
ms.assetid: 3af4fd3e-9ed5-4ed9-96fd-7031e5126fd1
caps.latest.revision: 7
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: d272ce98f7294e2c8ad2fb99d5d110f8af02bc7c
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="constant-and-global-variable-mappings"></a>定数とグローバル変数のマップ
ここで説明する汎用テキスト定数、グローバル変数、基本データ型のマッピングは TCHAR.H で定義されており、定数 `_UNICODE` または `_MBCS` がプログラムで定義されているかどうかに依存します。  
  
### <a name="generic-text-constant-and-global-variable-mappings"></a>汎用テキスト定数とグローバル変数のマッピング  
  
|汎用テキスト - オブジェクト名|SBCS (_UNICODE、_MBCS が未定義の場合)|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|----------------------------------|--------------------------------------------|--------------------|-----------------------|  
|`_TEOF`|`EOF`|`EOF`|`WEOF`|  
|`_tenviron`|`_environ`|`_environ`|`_wenviron`|  
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|  
  
## <a name="see-also"></a>関連項目  
 [汎用テキスト マップ](../c-runtime-library/generic-text-mappings.md)   
 [データ型のマップ](../c-runtime-library/data-type-mappings.md)   
 [ルーチンのマップ](../c-runtime-library/routine-mappings.md)   
 [汎用テキストのプログラム例](../c-runtime-library/a-sample-generic-text-program.md)   
 [汎用テキスト マップの使用](../c-runtime-library/using-generic-text-mappings.md)
