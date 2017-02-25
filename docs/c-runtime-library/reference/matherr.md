---
title: "_matherr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_matherr"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_matherr"
  - "matherr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_matherr 関数"
  - "matherr 関数"
ms.assetid: b600d66e-165a-4608-a856-8fb418d46760
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _matherr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

数値演算エラーを処理します。  
  
## 構文  
  
```  
  
      int _matherr(  
   struct _exception *except   
);  
```  
  
#### パラメーター  
 *ただし*  
 エラー情報を含む構造体へのポインター。  
  
## 戻り値  
 \_**matherr** でエラーや成功を示すに 0 以外の値を示すように、\- 0 を返します。  \_**matherr** が 0 を返す場合は、エラー メッセージを表示し、`errno` エラーは適切な値に設定されます。  \_**matherr** が 0 以外の値を返した場合、エラー メッセージは表示されず、`errno` は変更されません。  
  
 リターン コードに関する詳細については、「[" \_doserrno、errno、\_sys\_errlist、および\_sys\_nerr "](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 数値演算ライブラリの浮動小数点関数によって生成される\_**matherr** 関数にエラー。  エラーが検出されたときにこれらの関数呼び出しの\_**matherr**。  
  
 特殊なエラー処理のために、\_**matherr**の別の定義を提供できます。  C ランタイム ライブラリ \(Msvcr90.dll\) を動的にリンクされたなバージョンを使用する場合は、ユーザー定義のバージョンとクライアント実行可能ファイルの既定の\_**matherr** ルーチンを置き換えることができます。  ただし、DLL Msvcr90.dll のクライアントの既定の `_matherr` ルーチンを置き換えることはできません。  
  
 数値演算ルーチンでエラーが発生した場合、\_**matherr** は **\_exception** の型構造体へのポインターで引数として \(Math.h で定義\) が呼び出されます。  **\_exception** 構造体には、次の要素が含まれます。  
  
 **int type**  
 例外の種類。  
  
 **char \*name**  
 エラーが発生した関数の名前。  
  
 **double arg1**、**arg2**  
 関数の 1 番目と 2 番目の引数 \(存在する場合\)。  
  
 **double retval**  
 関数が返される値。  
  
 **型**、数値演算エラーの種類を指定します。  次の値の 1 と、Math.h で定義されます。  
  
 `_DOMAIN`  
 引数のドメイン エラー。  
  
 `_SING`  
 引数不適切。  
  
 `_OVERFLOW`  
 オーバーフローののエラー。  
  
 `_PLOSS`  
 重要度の部分的な消失  
  
 `_TLOSS`  
 重要度全体消失  
  
 `_UNDERFLOW`  
 結果を表すことが小さすぎる。この条件は、現在サポートされていません\)。  
  
 構造体メンバー **名前** は、エラーが発生した関数の名前を含む null で終わる文字列へのポインターです。  構造体メンバー **arg1** と **arg2** はエラーを発生させた値を指定します。1 個の引数を指定した場合 \(、**arg1**に格納されます\)。  
  
 特定のエラーの既定の戻り値は **retval**です。  戻り値を変更すると、実際にエラーが発生したかどうかを指定する必要があります。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_matherr`|\<math.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 使用例  
  
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
  
## 出力  
  
```  
Special: using absolute value: log: _DOMAIN error  
log( -2.0 ) = 6.931472e-001  
Special: using absolute value: log10: _DOMAIN error  
log10( -5.0 ) = 6.989700e-001  
Normal: log( 0.0 ) = -1.#INF00e+000  
```  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [Long Double 型](../../misc/long-double.md)