---
title: "_flushall | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _flushall
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _flushall
dev_langs:
- C++
helpviewer_keywords:
- flushall function
- flushing streams
- streams, flushing
- _flushall function
ms.assetid: 2cd73562-6d00-4ca2-b13c-80d0ae7870b5
caps.latest.revision: 16
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
ms.openlocfilehash: 230d52cf98e7dc563ea5d0067de7df31af8549f9
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="flushall"></a>_flushall
すべてのストリームをフラッシュし、すべてのバッファーをクリアします。  
  
## <a name="syntax"></a>構文  
  
```  
int _flushall( void );  
```  
  
## <a name="return-value"></a>戻り値  
 `_flushall` は、開いているストリーム (入力と出力) の数を返します。 エラーの戻り値はありません。  
  
## <a name="remarks"></a>コメント  
 既定では、`_flushall` 関数は、開いている出力ストリームに関連付けられているすべてのバッファーの内容を適切なファイルに書き込みます。 開いている入力ストリームに関連付けられているすべてのバッファーでは、現在の内容がクリアされます。 これらのバッファーは通常はオペレーティング システムによって保持され、データをディスクに自動的に書き込むための最適なタイミングが決定されます。タイミングとしては、バッファーがいっぱいになったとき、ストリームが閉じられるとき、プログラムがストリームを閉じずに正常に終了したときがあります。  
  
 読み取りの後に `_flushall` が呼び出されると、新しいデータが入力ファイルからバッファーに読み込まれます。 すべてのストリームは、`_flushall` の呼び出し後、開いたままになります。  
  
 ランタイム ライブラリのディスクへのコミットの機能を使用すると、重要なデータをオペレーティング システムのバッファーではなく、ディスクに直接書き込むことができます。 プログラムのオブジェクト ファイルを Commode.obj にリンクすると、既存のプログラムを書き直さずに、この機能を有効にできます。 そのようにした実行可能ファイルでは、`_flushall` を呼び出すと、すべてのバッファーの内容がディスクに書き込まれます。 `_flushall` と `fflush` だけが、Commode.obj の影響を受けます。  
  
 ディスクへのコミットの機能の制御については、「[ストリーム入出力](../../c-runtime-library/stream-i-o.md)」、「[fopen](../../c-runtime-library/reference/fopen-wfopen.md)」、および「[_fdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`_flushall`|\<stdio.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_flushall.c  
// This program uses _flushall  
// to flush all open buffers.  
  
#include <stdio.h>  
  
int main( void )  
{  
   int numflushed;  
  
   numflushed = _flushall();  
   printf( "There were %d streams flushed\n", numflushed );  
}  
```  
  
```Output  
There were 3 streams flushed  
```  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [_commit](../../c-runtime-library/reference/commit.md)   
 [fclose、_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)
