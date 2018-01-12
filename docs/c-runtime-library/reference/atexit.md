---
title: atexit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: atexit
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
f1_keywords: atexit
dev_langs: C++
helpviewer_keywords:
- processing, at exit
- atexit function
ms.assetid: 92c156d2-8052-4e58-96dc-00128baac6f9
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8e812f39041287d17ee87766f6971d299654f0f4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="atexit"></a>atexit
終了時に指定された関数を処理します。  
  
## <a name="syntax"></a>構文  
  
```  
int atexit(  
   void (__cdecl *func )( void )  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `func`  
 呼び出される関数。  
  
## <a name="return-value"></a>戻り値  
 `atexit` は正常終了した場合は 0、エラーが発生した場合は 0 以外の値を返します。  
  
## <a name="remarks"></a>コメント  
 `atexit` 関数には、プログラムが正常に終了したときに呼び出される関数 (`func`) のアドレスが渡されます。 `atexit` を連続して呼び出すと、後入れ先出し法 (LIFO) 順で実行される関数のレジスタが作成されます。 `atexit` に渡される関数は、パラメーターを受け取ることはできません。 `atexit` と `_onexit` は、ヒープを使用して関数のレジスタを保持します。 したがって、登録可能な関数の数は、ヒープ メモリの量によってのみ制限されます。  
  
 `atexit` 関数のコードには、`atexit` 関数が呼び出されたときに既にアンロードされている可能性がある DLL への依存関係を含めることはできません。  
  
 ANSI 準拠のアプリケーションを生成するには、ANSI 規格の `atexit` 関数を使用します (同様の `_onexit` 関数ではない)。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`atexit`|\<stdlib.h>|  
  
## <a name="example"></a>例  
 このプログラムは、`atexit` が呼び出された時に実行される関数のスタック上に 4 つの関数をプッシュします。 プログラムの終了時に、後入れ先出し法でこれらのプログラムが実行されます。  
  
```  
// crt_atexit.c  
#include <stdlib.h>  
#include <stdio.h>  
  
void fn1( void ), fn2( void ), fn3( void ), fn4( void );  
  
int main( void )  
{  
   atexit( fn1 );  
   atexit( fn2 );  
   atexit( fn3 );  
   atexit( fn4 );  
   printf( "This is executed first.\n" );  
}  
  
void fn1()  
{  
   printf( "next.\n" );  
}  
  
void fn2()  
{  
   printf( "executed " );  
}  
  
void fn3()  
{  
   printf( "is " );  
}  
  
void fn4()  
{  
   printf( "This " );  
}  
```  
  
```Output  
This is executed first.  
This is executed next.  
```  
  
## <a name="see-also"></a>参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [exit、_Exit、_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit、_onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)