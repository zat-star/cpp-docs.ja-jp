---
title: _free_locale | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _free_locale
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __free_locale
- free_locale
- _free_locale
dev_langs: C++
helpviewer_keywords:
- __free_locale function
- free_locale function
- locales, freeing
- _free_locale function
ms.assetid: 1f08d348-ab32-4028-a145-6cbd51b49af9
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fa4ee4f7be53898f38218b83f14c7579cc3206dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="freelocale"></a>_free_locale
ロケール オブジェクトを解放します。  
  
## <a name="syntax"></a>構文  
  
```  
void _free_locale(  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `locale`  
 解放するロケール オブジェクト。  
  
## <a name="remarks"></a>コメント  
 `_get_current_locale` または `_create_locale` の呼び出しから取得されたとロケール オブジェクトを解放するには、`_free_locale` 関数を使用します。  
  
 この関数の以前の名前 `__free_locale` (先頭に 2 個のアンダースコア) は、使用されなくなりました。  
  
## <a name="requirements"></a>必要条件  
  
|`Routine`|必須ヘッダー|  
|---------------|---------------------|  
|`_free_locale`|\<locale.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="see-also"></a>参照  
 [_get_current_locale](../../c-runtime-library/reference/get-current-locale.md)   
 [_create_locale、_wcreate_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)