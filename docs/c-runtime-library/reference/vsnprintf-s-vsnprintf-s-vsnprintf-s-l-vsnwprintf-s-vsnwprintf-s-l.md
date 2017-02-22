---
title: "vsnprintf_s、_vsnprintf_s、_vsnprintf_s_l、_vsnwprintf_s、_vsnwprintf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vsnwprintf_s"
  - "_vsnwprintf_s_l"
  - "_vsnprintf_s"
  - "vsnprintf_s"
  - "_vsnprintf_s_l"
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
  - "ntdll.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_vsnprintf_s"
  - "_vsntprintf_s"
  - "_vsnwprintf_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_vsnprintf_s 関数"
  - "_vsnprintf_s_l 関数"
  - "_vsntprintf_s 関数"
  - "_vsntprintf_s_l 関数"
  - "_vsnwprintf_s 関数"
  - "_vsnwprintf_s_l 関数"
  - "書式設定テキスト [C++]"
  - "vsnprintf_s 関数"
  - "vsnprintf_s_l 関数"
  - "vsntprintf_s 関数"
  - "vsntprintf_s_l 関数"
  - "vsnwprintf_s 関数"
  - "vsnwprintf_s_l 関数"
ms.assetid: 147ccfce-58c7-4681-a726-ef54ac1c604e
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 32
---
# vsnprintf_s、_vsnprintf_s、_vsnprintf_s_l、_vsnwprintf_s、_vsnwprintf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

引数リストへのポインターを使用して、書式付き出力を書き込みます。  これらの関数は、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、[vsnprintf、\_vsnprintf、\_vsnprintf\_l、\_vsnwprintf、\_vsnwprintf\_l](../../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) のセキュリティが強化されたバージョンです。  
  
## 構文  
  
```  
int vsnprintf_s(  
   char *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const char *format,  
   va_list argptr   
);  
int _vsnprintf_s(  
   char *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const char *format,  
   va_list argptr   
);  
int _vsnprintf_s_l(  
   char *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int _vsnwprintf_s(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vsnwprintf_s_l(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
template <size_t size>  
int _vsnprintf_s(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnwprintf_s(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
); // C++ only  
```  
  
#### パラメーター  
 `buffer`  
 出力の格納位置。  
  
 `sizeOfBuffer`  
 出力の `buffer` のサイズ \(文字数\)。  
  
 `count`  
 書き込む最大文字数 \(終端の null は含まない\)、または [\_TRUNCATE](../../c-runtime-library/truncate.md)。  
  
 `format`  
 書式の指定。  
  
 `argptr`  
 引数リストへのポインター。  
  
 `locale`  
 使用するロケール。  
  
 詳細については、「[scanf 関数と wscanf 関数の書式指定フィールド](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md)」を参照してください。  
  
## 戻り値  
 `vsnprintf_s` 関数、`_vsnprintf_s`  関数、および `_vsnwprintf_s` 関数は、書き込まれた文字数を返します。終端の null 文字は含まれません。出力エラーが発生した場合は、負の値を返します。  `vsnprintf_s` は `_vsnprintf_s` と同じです。  `vsnprintf_s` 関数は ANSI 規格に準拠する目的で含まれています。  `_vnsprintf` 関数は下位互換性のために残されています。  
  
 データと終端の null の格納に必要なストレージが `sizeOfBuffer` を超える場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。ただし、`count` が [\_TRUNCATE](../../c-runtime-library/truncate.md) の場合は、`buffer` に収まる限りの文字列が書き込まれ、\-1 が返されます。  無効なパラメーター ハンドラーの後に実行が継続されると、これらの関数は `buffer` を空の文字列に、`errno` を `ERANGE` に設定し、\-1 を返します。  
  
 `buffer` または `format` が `NULL` ポインターの場合、または `count` が 0 以下の場合は、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、\-1 を返します。  
  
### エラー条件  
  
|`Condition`|戻り値|`errno`|  
|-----------------|---------|-------------|  
|`buffer` が  `NULL`|\-1|`EINVAL`|  
|`format` が  `NULL`|\-1|`EINVAL`|  
|`count` \<\= 0|\-1|`EINVAL`|  
|`sizeOfBuffer` が小さすぎる \(および `count` \!\= `_TRUNCATE`\)|\-1 \(および `buffer` が空の文字列に設定される\)|`ERANGE`|  
  
## 解説  
 これらの関数は、引数リストへのポインターを使用し、指定されたデータを書式指定して `count` の文字数まで `buffer` が指すメモリに書き込み、終端の null を追加します。  
  
 `count` が [\_TRUNCATE](../../c-runtime-library/truncate.md) の場合、これらの関数は終端の null 用の空きを残して `buffer` に収まる限りの文字列を書き込みます。  文字列全体 \(終端の null を含む\) が `buffer` 内に収まる場合は、これらの関数は書き込まれた文字数を返します \(終端の null は含まない\)。それ以外の場合には \-1 を返し、切り捨てが行われたことを示します。  
  
 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
> [!IMPORTANT]
>  `format` にユーザー定義の文字列を指定しないでください。  詳細については、「[Avoiding Buffer Overruns](http://msdn.microsoft.com/library/windows/desktop/ms717795)」を参照してください。  
  
> [!NOTE]
>  終端の null 用の空きを確保するために、`count` を必ずバッファー長未満にするか、`_TRUNCATE` を使用します。  
  
 C\+\+ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる \(サイズの引数を指定する必要がなくなる\) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_vsntprintf_s`|`_vsnprintf_s`|`_vsnprintf_s`|`_vsnwprintf_s`|  
|`_vsntprintf_s_l`|`_vsnprintf_s_l`|`_vsnprintf_s_l`|`_vsnwprintf_s_l`|  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|省略可能なヘッダー|  
|----------|------------|---------------|  
|`vsnprintf_s`|\<stdio.h\> および \<stdarg.h\>|\<varargs.h\>\*|  
|`_vsnprintf_s`, `_vsnprintf_s_l`|\<stdio.h\> および \<stdarg.h\>|\<varargs.h\>\*|  
|`_vsnwprintf_s`, `_vsnwprintf_s_l`|\<stdio.h\> または \<wchar.h\>、および \<stdarg.h\>|\<varargs.h\>\*|  
  
 \* UNIX V との互換性用  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_vsnprintf_s.cpp  
#include <stdio.h>  
#include <wtypes.h>  
  
void FormatOutput(LPCSTR formatstring, ...)   
{  
   int nSize = 0;  
   char buff[10];  
   memset(buff, 0, sizeof(buff));  
   va_list args;  
   va_start(args, formatstring);  
   nSize = vsnprintf_s( buff, _countof(buff), _TRUNCATE, formatstring, args);  
   printf("nSize: %d, buff: %s\n", nSize, buff);  
}  
  
int main() {  
   FormatOutput("%s %s", "Hi", "there");  
   FormatOutput("%s %s", "Hi", "there!");  
   FormatOutput("%s %s", "Hi", "there!!");  
}  
```  
  
  **nSize: 8, buff: Hi there**  
**nSize: 9, buff: Hi there\!**  
**nSize: \-1, buff: Hi there\!**   
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [vprintf 系関数](../../c-runtime-library/vprintf-functions.md)   
 [fprintf、\_fprintf\_l、fwprintf、\_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf、\_printf\_l、wprintf、\_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf、\_sprintf\_l、swprintf、\_swprintf\_l、\_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg、va\_copy、va\_end、va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)