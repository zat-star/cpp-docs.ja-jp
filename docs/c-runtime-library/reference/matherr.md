---
title: _matherr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _matherr
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
- _matherr
- matherr
dev_langs:
- C++
helpviewer_keywords:
- _matherr function
- matherr function
ms.assetid: b600d66e-165a-4608-a856-8fb418d46760
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 843cfbbcac39af23aa6a3daaf70a786e8fa6866d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="matherr"></a>_matherr
数値演算エラーを処理します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      int _matherr(  
   struct _exception *except   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *except*  
 エラー情報を保持する構造体へのポインター。  
  
## <a name="return-value"></a>戻り値  
 _**matherr** は、エラーを示す 0 を返すか、成功を示す 0 以外の値を返します。 \_**matherr** が 0 を返す場合は、エラー メッセージを表示することができ、`errno` が該当するエラー値に設定されます。 \_**matherr** が 0 以外の値を返す場合は、エラー メッセージは表示されず、`errno` は変更されません。  
  
 リターン コードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 _**matherr** 関数は、数値演算ライブラリの浮動小数点関数によって生成されたエラーを処理します。 これらの関数は、エラーが検出されると \_**matherr** を呼び出します。  
  
 特殊なエラー処理を行う場合は、_**matherr** の別の定義を指定できます。 動的にリンクされたバージョンの C ランタイム ライブラリ (Msvcr90.dll) を使用する場合は、クライアントの実行可能ファイル内の既定の \_**matherr** ルーチンをユーザー定義のバージョンに置き換えることができます。 しかし、Msvcr90.dll の DLL クライアント内にある既定の `_matherr` ルーチンを置き換えることはできません。  
  
 数値演算ルーチンでエラーが発生した場合は、引数として **_exception** 型の構造体 (Math.h で定義) へのポインターを使用して _**matherr** が呼び出されます。 **_exception** 構造体には次の要素が含まれます。  
  
 **int type**  
 例外の種類。  
  
 **char \*name**  
 エラーが発生した関数の名前。  
  
 **double arg1**、**arg2**  
 関数への最初の引数と 2 番目の引数 (存在する場合)。  
  
 **double retval**  
 関数によって返される値。  
  
 **type** は数値演算エラーの種類を指定します。 Math.h で定義されている、次の値のいずれかになります。  
  
 `_DOMAIN`  
 引数のドメイン エラー。  
  
 `_SING`  
 引数の特異点。  
  
 `_OVERFLOW`  
 オーバーフロー範囲エラー。  
  
 `_PLOSS`  
 有効桁の部分的損失。  
  
 `_TLOSS`  
 有効桁の完全損失。  
  
 `_UNDERFLOW`  
 結果が小さすぎて表現できない。 (この条件は現在サポートされていません。)  
  
 構造体のメンバー **name** は、エラーの原因となった関数の名前を含む null で終わる文字列へのポインターです。 構造体のメンバー **arg1** と **arg2** は、エラーの原因となった値を指定します。 (指定されている引数が 1 つのみの場合は、**arg1** に格納されます。)  
  
 発生したエラーの既定の戻り値は **retval** です。 戻り値を変更する場合、戻り値はエラーが実際に発生したかどうかを指定する必要があります。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_matherr`|\<math.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```  
// crt_matherr.c  
/* illustrates writing an error routine for math   
 * functions. The error function must be:  
 *      _matherr  
 */  
  
#include <math.h>  
#include <string.h>  
#include <stdio.h>  
  
int main()  
{  
    /* Do several math operations that cause errors. The _matherr  
     * routine handles _DOMAIN errors, but lets the system handle  
     * other errors normally.  
     */  
    printf( "log( -2.0 ) = %e\n", log( -2.0 ) );  
    printf( "log10( -5.0 ) = %e\n", log10( -5.0 ) );  
    printf( "log( 0.0 ) = %e\n", log( 0.0 ) );  
}  
  
/* Handle several math errors caused by passing a negative argument  
 * to log or log10 (_DOMAIN errors). When this happens, _matherr  
 * returns the natural or base-10 logarithm of the absolute value  
 * of the argument and suppresses the usual error message.  
 */  
int _matherr( struct _exception *except )  
{  
    /* Handle _DOMAIN errors for log or log10. */  
    if( except->type == _DOMAIN )  
    {  
        if( strcmp( except->name, "log" ) == 0 )  
        {  
            except->retval = log( -(except->arg1) );  
            printf( "Special: using absolute value: %s: _DOMAIN "  
                     "error\n", except->name );  
            return 1;  
        }  
        else if( strcmp( except->name, "log10" ) == 0 )  
        {  
            except->retval = log10( -(except->arg1) );  
            printf( "Special: using absolute value: %s: _DOMAIN "  
                     "error\n", except->name );  
            return 1;  
        }  
    }  
    printf( "Normal: " );  
    return 0;    /* Else use the default actions */  
}  
```  
  
## <a name="output"></a>出力  
  
```  
Special: using absolute value: log: _DOMAIN error  
log( -2.0 ) = 6.931472e-001  
Special: using absolute value: log10: _DOMAIN error  
log10( -5.0 ) = 6.989700e-001  
Normal: log( 0.0 ) = -1.#INF00e+000  
```  
  
## <a name="see-also"></a>参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   