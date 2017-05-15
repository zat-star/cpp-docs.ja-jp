---
title: fflush | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fflush
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
- fflush
dev_langs:
- C++
helpviewer_keywords:
- streams, flushing
- flushing
- fflush function
ms.assetid: 8bbc753f-dc74-4e77-b563-74da2835e92b
caps.latest.revision: 18
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: f2a11a29ba0eec3c66cf23f72e8fe0e7106d5a5c
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="fflush"></a>fflush
ストリームをフラッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
int fflush(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
## <a name="return-value"></a>戻り値  
 バッファーが正常にフラッシュされた場合、`fflush` は 0 を返します。 指定したストリームにバッファーがないか、読み取り専用で開かれる場合にも、値 0 が返されます。 `EOF` の戻り値はエラーを示します。  
  
> [!NOTE]
>  `fflush` が `EOF` を返す場合、書き込みエラーのためにデータが失われることがあります。 重大なエラーのハンドラーを設定する場合、`setvbuf` 関数でバッファリングを無効にするか、ストリーム I/O 関数ではなく、低レベルの I/O ルーチン (`_open`、`_close`、`_write` など) を使用することをお勧めします。  
  
## <a name="remarks"></a>コメント  
 `fflush` 関数はストリーム `stream` をフラッシュします。 書き込みモードでストリームを開いた場合、または更新モードで開き、最後の操作が書き込みだった場合、基になるファイルまたはデバイスにストリーム バッファーの内容が書き込まれ、バッファーは破棄されます。 読み取りモードでストリームを開いた場合、またはストリームにバッファーがない場合、`fflush` の効果はなく、バッファーが保持されます。 `fflush` を呼び出すと、ストリームの `ungetc` に対する以前の呼び出しの効果は無効になります。 呼び出し後もストリームは開いたままになります。  
  
 `stream` が `NULL` の場合、開いている各ストリームで `fflush` を呼び出した場合と動作が同じになります。 書き込みモードで開いたすべてのストリームと、更新モードで開いて最後の操作が書き込みだったすべてのストリームは、フラッシュされます。 この呼び出しは、他のストリームに影響がありません。  
  
 バッファーは通常はオペレーティング システムによって保持され、データをディスクに自動的に書き込むための最適なタイミングが決定されます。タイミングとしては、バッファーがいっぱいになったとき、ストリームが閉じられるとき、プログラムがストリームを閉じずに正常に終了したときがあります。 ランタイム ライブラリのディスクへのコミットの機能を使用すると、重要なデータをオペレーティング システムのバッファーではなく、ディスクに直接書き込むことができます。 プログラムのオブジェクト ファイルを COMMODE.OBJ にリンクすると、既存のプログラムを書き直さずに、この機能を有効にできます。 そのようにした実行可能ファイルでは、`_flushall` を呼び出すと、すべてのバッファーの内容がディスクに書き込まれます。 `_flushall` と `fflush` だけが、COMMODE.OBJ の影響を受けます。  
  
 ディスクへのコミットの機能の制御については、「[ストリーム入出力](../../c-runtime-library/stream-i-o.md)」、「[fopen](../../c-runtime-library/reference/fopen-wfopen.md)」、および「[_fdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)」を参照してください。  
  
 この関数は呼び出し元スレッドをロックするため、スレッド セーフです。 ロックしないバージョンについては、「`_fflush_nolock`」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`fflush`|\<stdio.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_fflush.c  
#include <stdio.h>  
#include <conio.h>  
  
int main( void )  
{  
   int integer;  
   char string[81];  
  
   // Read each word as a string.  
   printf( "Enter a sentence of four words with scanf: " );  
   for( integer = 0; integer < 4; integer++ )  
   {  
      scanf_s( "%s", string, sizeof(string) );        
      printf( "%s\n", string );  
   }  
  
   // You must flush the input buffer before using gets.   
   // fflush on input stream is an extension to the C standard   
   fflush( stdin );     
   printf( "Enter the same sentence with gets: " );  
   gets_s( string, sizeof(string) );  
   printf( "%s\n", string );  
}  
```  
  
```Output  
  
      This is a test  
This is a test  
  
```  
  
```Output  
  
      This is a test  
This is a testEnter a sentence of four words with scanf: This is a test  
This  
is  
a  
test  
Enter the same sentence with gets: This is a test  
This is a test  
```  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fclose、_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)
