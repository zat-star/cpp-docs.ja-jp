---
title: "ロケールのカテゴリ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LC_MAX
- LC_MIN
- LC_MONETARY
- LC_TIME
- LC_NUMERIC
- LC_COLLATE
- LC_CTYPE
- LC_ALL
dev_langs:
- C++
helpviewer_keywords:
- LC_MIN constant
- LC_MONETARY constant
- LC_CTYPE constant
- locale constants
- LC_MAX constant
- LC_ALL constant
- LC_TIME constant
- LC_NUMERIC constant
- LC_COLLATE constant
ms.assetid: 868f1493-fe5d-4722-acab-bfcd374a063a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8e2188dc477a81477b65db22bcd06390a4b6773c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="locale-categories"></a>ロケールのカテゴリ
## <a name="syntax"></a>構文  
  
```  
  
#include <locale.h>  
  
```  
  
## <a name="remarks"></a>コメント  
 ロケールのカテゴリは、プログラムのロケール情報のどの部分を使用するかを指定する、ローカライズ ルーチンで使用されるマニフェスト定数です。 ロケールとは、地域性、つまり国や地域に関する情報であり、この情報に基づいてプログラムの特定の側面をカスタマイズできます。 ロケールに依存する領域としては、日付の形式や通貨値の表示形式などがあります。  
  
|ロケールのカテゴリ|影響を受けるプログラムの部分|  
|---------------------|-------------------------------|  
|`LC_ALL`|ロケール固有のすべての動作 (すべてのカテゴリ)|  
|`LC_COLLATE`|`strcoll` 関数と `strxfrm` 関数の動作|  
|`LC_CTYPE`|文字処理関数の動作 (影響を受けない **isdigit**、`isxdigit`、`mbstowcs``mbtowc` を除く)|  
|`LC_MAX`|`LC_TIME` と同じ|  
|`LC_MIN`|`LC_ALL` と同じ|  
|`LC_MONETARY`|`localeconv` 関数が返す通貨形式情報|  
|`LC_NUMERIC`|`printf` などの書式化出力ルーチン、データ変換ルーチン、`localeconv` 関数が返す通貨形式以外の形式情報などで使用される小数点文字|  
|`LC_TIME`|`strftime` 関数の動作|  
  
 例については、「[setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)」をご覧ください。  
  
## <a name="see-also"></a>参照  
 [localeconv](../c-runtime-library/reference/localeconv.md)   
 [setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcoll 関数](../c-runtime-library/strcoll-functions.md)   
 [strftime、wcsftime、_strftime_l、_wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)