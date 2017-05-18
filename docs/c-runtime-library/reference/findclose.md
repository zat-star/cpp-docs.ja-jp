---
title: _findclose | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _findclose
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _findclose
- findclose
dev_langs:
- C++
helpviewer_keywords:
- _findclose function
- findclose function
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
caps.latest.revision: 11
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: fcd76f8daec9c90374989a82f4b4b2f85b4cb5c7
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="findclose"></a>_findclose
指定した検索のハンドルを終了し、関連付けられているリソースを解放します。  
  
## <a name="syntax"></a>構文  
  
```  
int _findclose(   
   intptr_t handle   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `handle`  
 以前の `_findfirst` の呼び出しで返された検索ハンドル。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合、`_findclose` は 0 を返します。 -1 を返しますそれ以外の場合、設定と`errno`に`ENOENT`、以上に一致するファイルのことを示すが見つかりませんでした。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`_findclose`|\<io.h>|  
  
 互換性について詳しくは、「はじめに」の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [システム コール](../../c-runtime-library/system-calls.md)   
 [ファイル名検索関数](../../c-runtime-library/filename-search-functions.md)
