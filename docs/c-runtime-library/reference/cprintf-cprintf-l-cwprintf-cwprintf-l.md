---
title: "_cprintf、_cprintf_l、_cwprintf、_cwprintf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_cwprintf_l"
  - "_cprintf_l"
  - "_cwprintf"
  - "_cprintf"
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
  - "_cwprintf"
  - "cwprintf"
  - "tcprintf"
  - "_tcprintf"
  - "_cprintf"
  - "cwprintf_l"
  - "tcprintf_l"
  - "_tcprintf_l"
  - "cprintf_l"
  - "_cprintf_l"
  - "_cwprintf_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_cprintf 関数"
  - "_cprintf_l 関数"
  - "_cwprintf 関数"
  - "_cwprintf_l 関数"
  - "_tcprintf 関数"
  - "_tcprintf_l 関数"
  - "文字, 印刷 (コンソールに)"
  - "cprintf_l 関数"
  - "cwprintf 関数"
  - "cwprintf_l 関数"
  - "出力 (コンソールに文字を)"
  - "tcprintf 関数"
  - "tcprintf_l 関数"
ms.assetid: 67ffefd4-45b3-4be0-9833-d8d26ac7c4e2
caps.latest.revision: 34
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 34
---
# _cprintf、_cprintf_l、_cwprintf、_cwprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

書式化してコンソールに出力します。  セキュリティが強化されたバージョンを使用できるようになりました。「[\_cprintf\_s、\_cprintf\_s\_l、\_cwprintf\_s、\_cwprintf\_s\_l](../../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)」を参照してください。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
int _cprintf(   
   const char * format [,   
   argument] ...   
);  
int _cprintf_l(   
   const char * format,  
   locale_t locale [,  
   argument] …   
);  
int _cwprintf(  
   const wchar * format [,   
   argument] …  
);  
int _cwprintf_l(  
   const wchar * format,  
   locale_t locale [,   
   argument] …  
);  
```  
  
#### パラメーター  
 `format`  
 書式指定文字列。  
  
 `argument`  
 省略可能なパラメーター。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 出力された文字数。  
  
## 解説  
 これらの関数は、文字を出力する `` `_putch` 関数 \(`_cwprintf` の場合は `_putwch`\) を使用して、一連の文字や値を書式化して直接コンソールに出力します。  各 `argument` \(指定されている場合\) は、`format` 中の対応する書式指定に応じて変換され、格納されます。  書式は、[printf](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md) 関数のパラメーター `format` と同じ形式および機能を保持します。  `fprintf`、`printf`、`sprintf` の各関数とは異なり、`_cprintf` も `_cwprintf` も、出力時にライン フィード文字をキャリッジ リターンとライン フィード \(CR\-LF: carriage return–line feed\) の組み合わせに変換しません。  
  
 `_cwprintf` を Windows NT で使用すると、Unicode 文字が表示される点に注意してください。  `_cprintf` と異なり、`_cwprintf` はコンソールの現在のロケール設定を使用します。  
  
 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在のロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
 `_cprintf` は、`format` パラメーターを検証します。  `format` が null ポインターの場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、この関数は無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、関数は \-1 を返し、`errno` を `EINVAL` に設定します。  
  
> [!IMPORTANT]
>  `format` にユーザー定義の文字列を指定しないでください。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tcprintf`|`_cprintf`|`_cprintf`|`_cwprintf`|  
|`_tcprintf_l`|`_cprintf_l`|`_cprintf_l`|`_cwprintf_l`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_cprintf`,`_cprintf_l`|\<conio.h\>|  
|`_cwprintf`, `_cwprintf_l`|\<conio.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
  **\-16  001d  62511  A Test**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [コンソール入出力とポート入出力](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cscanf、\_cscanf\_l、\_cwscanf、\_cwscanf\_l](../../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)   
 [fprintf、\_fprintf\_l、fwprintf、\_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf、\_printf\_l、wprintf、\_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf、\_sprintf\_l、swprintf、\_swprintf\_l、\_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [vfprintf、\_vfprintf\_l、vfwprintf、\_vfwprintf\_l](../../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)   
 [\_cprintf\_s、\_cprintf\_s\_l、\_cwprintf\_s、\_cwprintf\_s\_l](../../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)   
 [\_cprintf\_p、\_cprintf\_p\_l、\_cwprintf\_p、\_cwprintf\_p\_l](../../c-runtime-library/reference/cprintf-p-cprintf-p-l-cwprintf-p-cwprintf-p-l.md)   
 [書式指定構文: printf 関数と wprintf 関数](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md)