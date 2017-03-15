---
title: "va_arg、va_copy、va_end、va_start | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- va_arg
- va_end
- va_copy
- va_start
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
- va_arg
- va_start
- va_list
- va_alist
- va_dcl
- va_copy
- va_end
dev_langs:
- C++
helpviewer_keywords:
- variable argument lists, accessing
- va_start macro
- va_arg macro
- va_end macro
- arguments [C++], argument lists
- va_list macro
- va_dcl macro
- va_alist macro
- va_copy macro
ms.assetid: a700dbbd-bfe5-4077-87b6-3a07af74a907
caps.latest.revision: 20
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
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 5caea89460070402fc8dc5b38912e290d4c5798d
ms.lasthandoff: 02/24/2017

---
# <a name="vaarg-vacopy-vaend-vastart"></a>va_arg、va_copy、va_end、va_start
可変個引数リストにアクセスする。  
  
## <a name="syntax"></a>構文  
  
```  
type va_arg(  
   va_list arg_ptr,  
   type   
);
void va_copy(  
   va_list dest,  
   va_list src  
); // (ISO C99 and later)  
void va_end(  
   va_list arg_ptr   
);  
void va_start(  
   va_list arg_ptr,  
   prev_param   
); // (ANSI C89 and later)  
void va_start(  
   arg_ptr   
);  // (deprecated Pre-ANSI C89 standardization version)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `type`  
 取得される引数の型。  
  
 `arg_ptr`  
 引数リストへのポインター。  
  
 `dest`  
 `src` で初期化される引数リストへのポインター  
  
 `src`  
 `dest` へコピーされる、初期化された引数のリストへのポインター。  
  
 `prev_param`  
 最初の省略可能な引数に先行するパラメーター。  
  
## <a name="return-value"></a>戻り値  
 `va_arg` は現在の引数を返します。 `va_copy`、`va_start`、および `va_end` は値を返しません。  
  
## <a name="remarks"></a>コメント  
 関数が可変個の引数を受け取る場合、`va_arg`、`va_copy`、`va_end`、および `va_start` の各マクロを使用することで、関数は移植性の高い方法で引数にアクセスできます。 このマクロには&2; 種類のバージョンがあります。STDARG.H で定義されているマクロは、ISO C99 標準に準拠します。VARARGS.H で定義されているマクロは使用されなくなりましたが、ANSI C89 標準以前に作成されたコードの下位互換性のために残されています。  
  
 これらのマクロは、関数が固定の個数の必須の引数の後に、省略可能な引数を可変個数受け取るものと想定します。 必須の引数は、関数の通常のパラメーターのように宣言され、パラメーター名でアクセスできます。 省略可能な引数は、STDARG.H (または、ANSI C89 標準以前に書かれたコードの場合は VARARGS.H) のマクロを使用してアクセスします。これらのマクロは、ポインターを引数リストの最初の省略可能な引数へセットし、リストから引数を取得し引数の処理が終了するとポインターをリセットします。  
  
 STDARG.H で定義されている C 標準マクロは次のように使用されます。  
  
-   `va_start` は、`arg_ptr` を、関数に渡された引数のリストの最初の省略可能な引数に設定します。 引数 `arg_ptr` には `va_list` 型を指定しなければなりません。 引数 `prev_param` は、引数リストの最初の省略可能な引数の前に記述する、必須のパラメーターの名前です。 `prev_param` がレジスタのストレージ クラスで宣言されている場合、マクロの動作は未定義です。 `va_start` は `va_arg` が初めて使用される前に使用する必要があります。  
  
-   `va_arg` は次の引数がどこで開始するかを決定するために、`type` で指定された位置から `arg_ptr` の値を取得し、`arg_ptr` のサイズを使用して、リストの次の引数を指すように `type` をインクリメントします。 `va_arg` は、リストから引数を取得するために関数内で何回でも使用できます。  
  
-   `va_copy` は、現在の状態の引数のリストのコピーを作成します。 `src` パラメーターは、`va_start` で既に初期化済みである必要があります。これは `va_arg` の呼び出しで更新されていることは認められますが、`va_end` でリセットされていないことが必要です。 `va_arg` から `dest` によって取得される次の引数は `src` から取得される次の引数と同じです。  
  
-   `va_end` は、すべての引数の取得後にポインターを **NULL** にリセットします。 その関数が制御を返す前に、`va_end` が `va_start` か `va_copy` で初期化された各引数リストで呼び出される必要があります。  
  
> [!NOTE]
>  VARARGS.H のマクロは使用されておらず、C89 ANSI 規格以前に作成されたコードとの下位互換性のためだけに残されています。 それ以外の場合は、STDARGS.H のマクロを使用します。  
  
 これらのマクロを使用するプログラムを [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md) でコンパイルすると、ネイティブ言語ランタイムと共通言語ランタイム (CLR) の型システムの違いにために予期しない結果が発生することがあります。 次のプログラムを検討します。  
  
```  
#include <stdio.h>  
#include <stdarg.h>  
  
void testit (int i, ...)  
{  
    va_list argptr;  
    va_start(argptr, i);  
  
    if (i == 0)  
    {  
        int n = va_arg(argptr, int);  
        printf("%d\n", n);  
    }  
    else  
    {  
        char *s = va_arg(argptr, char*);  
        printf("%s\n", s);  
    }  

    va_end(argptr);  
}  
  
int main()  
{  
    testit(0, 0xFFFFFFFF); // 1st problem: 0xffffffff is not an int  
    testit(1, NULL);       // 2nd problem: NULL is not a char*  
}  
```  
  
 `testit` では&2; 番目のパラメーターが `int` または `char*` である必要があることに注意してください。 渡される引数は 0xffffffff (`unsigned int` であり、`int` ではない) と `NULL` (実際には `int` であり、`char*` ではない) です。 ネイティブ コードの場合にプログラムをコンパイルすると、次の出力が生成されます。  
  
```Output  
-1  
  
(null)  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<stdio.h> および \<stdarg.h>  
  
 **非推奨ヘッダー:** \<varargs.h>  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```  
// crt_va.c  
/* Compile with: cl /W3 /Tc crt_va.c  
 * The program below illustrates passing a variable  
 * number of arguments using the following macros:  
 *      va_start            va_arg              va_copy  
 *      va_end              va_list  
 */  
  
#include <stdio.h>  
#include <stdarg.h>  
#include <math.h>  
  
double deviation(int first, ...);  
  
int main( void )  
{  
    /* Call with 3 integers (-1 is used as terminator). */  
    printf("Deviation is: %f\n", deviation(2, 3, 4, -1 ));  
  
    /* Call with 4 integers. */  
    printf("Deviation is: %f\n", deviation(5, 7, 9, 11, -1));  
  
    /* Call with just -1 terminator. */  
    printf("Deviation is: %f\n", deviation(-1));  
}  
  
/* Returns the standard deviation of a variable list of integers. */  
double deviation(int first, ...)  
{  
    int count = 0, i = first;  
    double mean = 0.0, sum = 0.0;  
    va_list marker;  
    va_list copy;  
  
    va_start(marker, first);     /* Initialize variable arguments. */  
    va_copy(copy, marker);       /* Copy list for the second pass */  
    while (i != -1)  
    {  
        sum += i;  
        count++;  
        i = va_arg(marker, int);  
    }  
    va_end(marker);              /* Reset variable argument list. */  
    mean = sum ? (sum / count) : 0.0;  
  
    i = first;                  /* reset to calculate deviation */  
    sum = 0.0;  
    while (i != -1)  
    {  
        sum += (i - mean)*(i - mean);  
        i = va_arg(copy, int);  
    }  
    va_end(copy);               /* Reset copy of argument list. */  
    return count ? sqrt(sum / count) : 0.0;  
}  
  
```  
  
## <a name="output"></a>出力  
  
```Output  
Deviation is: 0.816497  
Deviation is: 2.236068  
Deviation is: 0.000000  
  
```  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 [System::ParamArrayAttribute Class](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx)  
  
## <a name="see-also"></a>関連項目  
 [引数へのアクセス](../../c-runtime-library/argument-access.md)   
 [vfprintf、_vfprintf_l、vfwprintf、_vfwprintf_l](../../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)
