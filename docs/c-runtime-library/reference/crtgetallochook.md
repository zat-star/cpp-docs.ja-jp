---
title: _CrtGetAllocHook | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtGetAllocHook
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
apitype: DLLExport
f1_keywords:
- CrtGetAllocHook
- _CrtGetAllocHook
dev_langs:
- C++
helpviewer_keywords:
- _CrtGetAllocHook function
- CrtGetAllocHook function
ms.assetid: 036acf7c-547a-4b3f-a636-80451070d7ed
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 90da1fce074f52389ba7b55c481e125652ee6696
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="crtgetallochook"></a>_CrtGetAllocHook
C ランタイム デバッグのメモリ割り当てプロセスにフックする現在のクライアント定義割り当て関数を取得します (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
_CRT_ALLOC_HOOK _CrtGetAllocHook( void );  
```  
  
## <a name="return-value"></a>戻り値  
 現在定義されている割り当てフック関数を返します。  
  
## <a name="remarks"></a>コメント  
 `_CrtGetAllocHook` は、C ランタイム デバッグ ライブラリのメモリ割り当てプロセスのために、現在のクライアント定義アプリケーションのフック関数を取得します。  
  
 フックをサポートするその他のランタイム関数の使い方の詳細と、独自のクライアント定義フック関数の記述方法については、「[デバッグ用フック関数の作成](/visualstudio/debugger/debug-hook-function-writing)」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_CrtGetAllocHook`|\<crtdbg.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="see-also"></a>関連項目  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [_CrtSetAllocHook](../../c-runtime-library/reference/crtsetallochook.md)
