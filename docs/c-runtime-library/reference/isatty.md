---
title: _isatty | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _isatty
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
- _isatty
dev_langs:
- C++
helpviewer_keywords:
- isatty function
- character device checking
- _isatty function
- checking character devices
ms.assetid: 9f1b2e87-0cd7-4079-b187-f2b7ca15fcbe
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: dbffe7023e178949f7167f283107e147ed13cb66
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="isatty"></a>_isatty
ファイル記述子が文字デバイスに関連付けられているかどうかを判定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      int _isatty(  
int fd   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fd`  
 調べるデバイスを参照するファイル記述子。  
  
## <a name="return-value"></a>戻り値  
 `_isatty` は、記述子がキャラクター デバイスに関連付けられている場合、0 以外の値を返します。 それ以外の場合、`_isatty` は 0 を返します。  
  
## <a name="remarks"></a>コメント  
 `_isatty` 関数では、`fd` がキャラクター デバイス (端末、コンソール、プリンター、またはシリアル ポート) に関連付けられているかどうかを調べます。  
  
 この関数は、`fd` パラメーターを検証します。 `fd` が不適切なファイル ポインターである場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は 0 を返し、`errno` を `EBADF` に設定します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_isatty`|\<io.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```  
// crt_isatty.c  
/* This program checks to see whether  
 * stdout has been redirected to a file.  
 */  
  
#include <stdio.h>  
#include <io.h>  
  
int main( void )  
{  
   if( _isatty( _fileno( stdout ) ) )  
      printf( "stdout has not been redirected to a file\n" );  
   else  
      printf( "stdout has been redirected to a file\n");  
}  
```  
  
## <a name="sample-output"></a>出力例  
  
```  
stdout has not been redirected to a file  
```  
  
## <a name="see-also"></a>関連項目  
 [ファイル処理](../../c-runtime-library/file-handling.md)
