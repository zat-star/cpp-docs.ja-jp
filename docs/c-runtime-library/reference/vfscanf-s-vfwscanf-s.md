---
title: "vfscanf_s、vfwscanf_s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- vfscanf_s
- vfwscanf_s
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
- vfscanf_s
- vfwscanf_s
- _vftscanf_s
dev_langs: C++
ms.assetid: 9b0133f0-9a18-4581-b24b-3b72683ad432
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c1012a87cd2f5b73818000877216839f881c309c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="vfscanfs-vfwscanfs"></a>vfscanf_s、vfwscanf_s
ストリームから書式化されたデータを読み出します。 これらのバージョンの vfscanf、vfwscanf は、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンです。  
  
## <a name="syntax"></a>構文  
  
```  
int vfscanf_s(   
   FILE *stream,  
   const char *format,  
   va_list arglist  
);  
int vfwscanf_s(   
   FILE *stream,  
   const wchar_t *format,  
   va_list arglist  
);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
 `format`  
 書式指定文字列。  
  
 `arglist`  
 可変個引数リスト。  
  
## <a name="return-value"></a>戻り値  
 これらの関数は、正常に変換および代入されたフィールドの数を返します。読み込まれただけで代入されなかったフィールドは戻り値には含まれません。 戻り値が 0 の場合は、代入されたフィールドがなかったことを示します。 エラーが発生した場合や、最初の変換の前にファイル ストリームの終端を検出した場合、`EOF` および `vfscanf_s` は `vfwscanf_s` を返します。  
  
 これらの関数では、パラメーターの検証が行われます。 `stream` が無効なファイル ポインターの場合、または `format` が Null ポインターの場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、これらの関数は無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、これらの関数は `EOF` を返し、 `errno` を `EINVAL`に設定します。  
  
## <a name="remarks"></a>コメント  
 `vfscanf_s` 関数は、`stream` の現在位置から `arglist` 引数リスト (ある場合) で指定された位置にデータを読み込みます。 リストの各引数は、`format` の型指定子に対応する型の変数へのポインターにする必要があります。 `format` は、入力フィールドの解釈を制御し、`scanf_s` の引数 `format` と同じ形式と機能を持ちます。`format` の詳細については、「[scanf 関数と wscanf 関数の書式指定フィールド](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)」を参照してください。 `vfwscanf_s` 関数は、`vfscanf_s` 関数のワイド文字バージョンです。`vfwscanf_s` の format 引数は、ワイド文字列です。 ストリームが ANSI モードで開かれている場合、これらの関数の動作は同じになります。 `vfscanf_s` では、UNICODE ストリームからの入力はサポートされていません。  
  
 セキュリティが強化された関数 (`_s` サフィックス付き) とその他のバージョンの関数との主な違いは、セキュリティが強化された関数では、`c`、`C`、`s`、`S`、および `[` の各型フィールドを使用するとき、引数として、それぞれの変数の直後にフィールドのサイズを渡す必要がある点です。 詳細については、「[scanf_s、_scanf_s_l、wscanf_s、_wscanf_s_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)」と「[scanf 関数の文字幅指定](../../c-runtime-library/scanf-width-specification.md)」を参照してください。  
  
> [!NOTE]
>  サイズ パラメーターは `unsigned` 型ではなく、`size_t` 型です。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vftscanf_s`|`vfscanf_s`|`vfscanf_s`|`vfwscanf_s`|  
  
## <a name="requirements"></a>必要条件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`vfscanf_s`|\<stdio.h>|  
|`vfwscanf_s`|\<stdio.h> または \<wchar.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_vfscanf_s.c  
// compile with: /W3  
// This program writes formatted  
// data to a file. It then uses vfscanf_s to  
// read the various data back from the file.  
  
#include <stdio.h>  
#include <stdarg.h>  
#include <stdlib.h>  
  
FILE *stream;  
  
int call_vfscanf_s(FILE * istream, char * format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vfscanf_s(istream, format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int main(void)  
{  
    long l;  
    float fp;  
    char s[81];  
    char c;  
  
    if (fopen_s(&stream, "vfscanf_s.out", "w+") != 0)  
    {  
        printf("The file vfscanf_s.out was not opened\n");  
    }  
    else  
    {  
        fprintf(stream, "%s %ld %f%c", "a-string",  
            65000, 3.14159, 'x');  
        // Security caution!  
        // Beware loading data from a file without confirming its size,  
        // as it may lead to a buffer overrun situation.  
  
        // Set pointer to beginning of file:  
        fseek(stream, 0L, SEEK_SET);  
  
        // Read data back from file:  
        call_vfscanf_s(stream, "%s %ld %f%c", s, _countof(s), &l, &fp, &c, 1);  
  
        // Output data read:   
        printf("%s\n", s);  
        printf("%ld\n", l);  
        printf("%f\n", fp);  
        printf("%c\n", c);  
  
        fclose(stream);  
    }  
}  
  
```  
  
```Output  
a-string  
65000  
3.141590  
x  
```  
  
## <a name="see-also"></a>参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [_cscanf_s、_cscanf_s_l、_cwscanf_s、_cwscanf_s_l](../../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)   
 [fprintf_s、_fprintf_s_l、fwprintf_s、_fwprintf_s_l](../../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)   
 [scanf_s、_scanf_s_l、wscanf_s、_wscanf_s_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [sscanf_s、_sscanf_s_l、swscanf_s、_swscanf_s_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)   
 [fscanf、_fscanf_l、fwscanf、_fwscanf_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [vfscanf、vfwscanf](../../c-runtime-library/reference/vfscanf-vfwscanf.md)