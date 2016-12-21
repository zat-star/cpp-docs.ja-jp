---
title: "_vscprintf_p、_vscprintf_p_l、_vscwprintf_p、_vscwprintf_p_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vscprintf_p_l"
  - "_vscprintf_p"
  - "_vscwprintf_p_l"
  - "_vscwprintf_p"
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
  - "_vscprintf_p"
  - "_vscprintf_p_l"
  - "vscwprintf_p"
  - "vscprintf_p"
  - "vscwprintf_p_l"
  - "_vscwprintf_p_l"
  - "vscprintf_p_l"
  - "_vscwprintf_p"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_vscprintf_p 関数"
  - "_vscprintf_p_l 関数"
  - "_vsctprintf_p 関数"
  - "_vsctprintf_p_l 関数"
  - "_vscwprintf_p 関数"
  - "_vscwprintf_p_l 関数"
  - "vscprintf_p 関数"
  - "vscprintf_p_l 関数"
  - "vsctprintf_p 関数"
  - "vsctprintf_p_l 関数"
  - "vscwprintf_p 関数"
  - "vscwprintf_p_l 関数"
ms.assetid: 5da920b3-8652-4ee9-b19e-5aac3ace9d03
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _vscprintf_p、_vscprintf_p_l、_vscwprintf_p、_vscwprintf_p_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

引数一覧へのポインターを使用して書式指定された文字列の文字数を返します。その際に引数を使用する順序を指定できます。  
  
## 構文  
  
```  
int _vscprintf_p(  
   const char *format,  
   va_list argptr   
);  
int _vscprintf_p _l(  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int _vscwprintf_p (  
   const wchar_t *format,  
   va_list argptr   
);  
int _vscwprintf_p _l(  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
```  
  
#### パラメーター  
 `format`  
 書式指定文字列。  
  
 `argptr`  
 引数リストへのポインター。  
  
 `locale`  
 使用するロケール。  
  
 詳細については、「[scanf 関数と wscanf 関数の書式指定フィールド](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md)」を参照してください。  
  
## 戻り値  
 `_vscprintf_p` 関数は、引数リストが指す文字列が、指定の書式化コードを使用して出力されるか、またはファイルやバッファーに送信された場合に生成される文字数を返します。  返される値には、終端の NULL 文字は含まれません。  ワイド文字の場合は、`_vscwprintf_p` が同じ機能を実行します。  
  
## 解説  
 これらの関数は、引数を使用する順序を指定できることを除いて `_vscprintf` と `_vscwprintf` と同じです。  詳細については、「[printf\_p の位置指定パラメーター](../../c-runtime-library/printf-p-positional-parameters.md)」を参照してください。  
  
 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
 `format` が null ポインターの場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、関数は \-1 を返し、`errno` を `EINVAL` に設定します。  
  
> [!IMPORTANT]
>  `format` がユーザー定義文字列の場合は、終端が null で、正しい数と型のパラメーターが含まれていることを必ず確認してください。  詳細については、「[Avoiding Buffer Overruns](http://msdn.microsoft.com/library/windows/desktop/ms717795)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_vsctprintf_p`|`_vscprintf_p`|`_vscprintf_p`|`_vscwprintf_p`|  
|`_vsctprintf_p_l`|`_vscprintf_p_l`|`_vscprintf_p_l`|`_vscwprintf_p_l`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_vscprintf_p`, `_vscprintf_p_l`|\<stdio.h\>|  
|`_vscwprintf_p`, `_vscwprintf_p_l`|\<stdio.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 「[vsprintf](../../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)」の例を参照してください。  
  
## 参照  
 [vprintf 系関数](../../c-runtime-library/vprintf-functions.md)   
 [\_scprintf\_p、\_scprintf\_p\_l、\_scwprintf\_p、\_scwprintf\_p\_l](../../c-runtime-library/reference/scprintf-p-scprintf-p-l-scwprintf-p-scwprintf-p-l.md)   
 [\_vscprintf、\_vscprintf\_l、\_vscwprintf、\_vscwprintf\_l](../../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)