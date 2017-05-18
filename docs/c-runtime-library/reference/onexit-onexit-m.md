---
title: "_onexit、_onexit_m | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _onexit
- _onexit_m
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
- _onexit
- onexit_m
- onexit
- _onexit_m
dev_langs:
- C++
helpviewer_keywords:
- onexit function
- registry, registering exit routines
- _onexit_m function
- onexit_m function
- _onexit function
- registering exit routines
- registering to be called on exit
ms.assetid: 45743298-0e2f-46cf-966d-1ca44babb443
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
ms.openlocfilehash: 50070672e990333073f5ad7f7ba604110c3a3cfa
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="onexit-onexitm"></a>_onexit、_onexit_m
終了時に呼び出されるルーチンを登録します。  
  
## <a name="syntax"></a>構文  
  
```  
_onexit_t _onexit(  
   _onexit_t function  
);  
_onexit_t_m _onexit_m(  
   _onexit_t_m function  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `function`  
 終了時に呼び出される関数へのポインター。  
  
## <a name="return-value"></a>戻り値  
 `_onexit` は、成功した場合、関数へのポインターを返し、関数ポインターを格納する領域がない場合は、`NULL` を返します。  
  
## <a name="remarks"></a>コメント  
 `_onexit` 関数には、プログラムが正常に終了したときに呼び出される関数 (`function`) のアドレスが渡されます。 `_onexit` を連続して呼び出すと、LIFO (後入先出法) 順で実行される関数のレジスタが作成されます。 `_onexit` に渡される関数は、パラメーターを受け取ることはできません。  
  
 `_onexit` が DLL 内から呼び出されると、`_onexit` で登録されたルーチンは、`DllMain` が DLL_PROCESS_DETACH で呼び出された後、DLL のアンロード時に実行されます。  
  
 `_onexit` は Microsoft 拡張機能です。 ANSI の移植性のためには、[atexit](../../c-runtime-library/reference/atexit.md) を使用します。 `_onexit_m` バージョンの関数は、混在モード用です。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_onexit`|\<stdlib.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_onexit.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
/* Prototypes */  
int fn1(void), fn2(void), fn3(void), fn4 (void);  
  
int main( void )  
{  
   _onexit( fn1 );  
   _onexit( fn2 );  
   _onexit( fn3 );  
   _onexit( fn4 );  
   printf( "This is executed first.\n" );  
}  
  
int fn1()  
{  
   printf( "next.\n" );  
   return 0;  
}  
  
int fn2()  
{  
   printf( "executed " );  
   return 0;  
}  
  
int fn3()  
{  
   printf( "is " );  
   return 0;  
}  
  
int fn4()  
{  
   printf( "This " );  
   return 0;  
}  
```  
  
## <a name="output"></a>出力  
  
```  
This is executed first.  
This is executed next.  
```  
  
## <a name="see-also"></a>関連項目  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [exit、_Exit、_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [__dllonexit](../../c-runtime-library/dllonexit.md)
