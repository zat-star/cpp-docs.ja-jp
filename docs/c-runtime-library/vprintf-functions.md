---
title: "vprintf 系関数 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "vprintf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "書式設定テキスト [C++]"
  - "vprintf 関数"
ms.assetid: 02ac7c51-eab1-4bf0-bf4c-77065e3fa744
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# vprintf 系関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`vprintf` の関数は、引数リストへのポインターを使用し、特定のデスティネーションに指定したデータを書き込みます。  関数は、パラメーターの検証関数では、パラメーターは書式指定文字列で使用する順序を指定するための前の文字列、出力先とサポートで使用するかどうかが異なります。  
  
|||  
|-|-|  
|[\_vcprintf、\_vcwprintf](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md)|[vfprintf、vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|  
|[\_vfprintf\_p、\_vfprintf\_p\_l、\_vfwprintf\_p、\_vfwprintf\_p\_l](../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)|[vfprintf\_s、\_vfprintf\_s\_l、vfwprintf\_s、\_vfwprintf\_s\_l](../Topic/vfprintf_s,%20_vfprintf_s_l,%20vfwprintf_s,%20_vfwprintf_s_l.md)|  
|[vprintf、vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|[\_vprintf\_p、\_vprintf\_p\_l、\_vwprintf\_p、\_vwprintf\_p\_l](../c-runtime-library/reference/vprintf-p-vprintf-p-l-vwprintf-p-vwprintf-p-l.md)|  
|[vprintf\_s、\_vprintf\_s\_l、vwprintf\_s、\_vwprintf\_s\_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)|[vsprintf、vswprintf](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)|  
|[\_vsprintf\_p、\_vsprintf\_p\_l、\_vswprintf\_p、\_vswprintf\_p\_l](../Topic/_vsprintf_p,%20_vsprintf_p_l,%20_vswprintf_p,%20_vswprintf_p_l.md)|[vsprintf\_s、\_vsprintf\_s\_l、vswprintf\_s、\_vswprintf\_s\_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)|  
|[\_vscprintf、\_vscprintf\_l、\_vscwprintf、\_vscwprintf\_l](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|[\_vsnprintf、\_vsnwprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md)|  
  
## 解説  
 `vprintf` の機能を次の表に示すように、対応する関数と似ています。  ただし、`vprintf` の各関数は、引数リストに対応する機能の各関数が引数リストを受け取る場合は、ポインターを受け取ります。  
  
 前への出力のこれらの関数の形式のデータは次のとおりです。  
  
|関数|対応する関数|出力先|パラメーターの検証|位置指定パラメーター サポート|  
|--------|------------|---------|---------------|---------------------|  
|`_vcprintf`|[\_cprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|コンソール|null をチェックします。|no|  
|`_vcwprintf`|[\_cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|コンソール|null をチェックします。|no|  
|`vfprintf`|[fprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Stream*|null をチェックします。|no|  
|**vfprintf\_p**|[fprintf\_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Stream*|空白と有効な形式を確認します。|可|  
|`vfprintf_s`|[fprintf\_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Stream*|空白と有効な形式を確認します。|no|  
|`vfwprintf`|[fwprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Stream*|null をチェックします。|no|  
|**vfwprintf\_p**|[fwprintf\_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Stream*|空白と有効な形式を確認します。|可|  
|`vfwprintf_s`|[fwprintf\_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Stream*|空白と有効な形式を確認します。|no|  
|`vprintf`|[printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|null をチェックします。|no|  
|**vprintf\_p**|[printf\_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|空白と有効な形式を確認します。|可|  
|`vprintf_s`|[printf\_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|空白と有効な形式を確認します。|no|  
|`vwprintf`|[wprintf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|null をチェックします。|no|  
|**vwprintf\_p**|[wprintf\_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|空白と有効な形式を確認します。|可|  
|`vwprintf_s`|[wprintf\_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|空白と有効な形式を確認します。|no|  
|**vsprintf**|[sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|buffer が指すメモリ|null をチェックします。|no|  
|**vsprintf\_p**|[sprintf\_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|buffer が指すメモリ|空白と有効な形式を確認します。|可|  
|`vsprintf_s`|[sprintf\_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|buffer が指すメモリ|空白と有効な形式を確認します。|no|  
|`vswprintf`|[swprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|buffer が指すメモリ|null をチェックします。|no|  
|**vswprintf\_p**|[swprintf\_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|buffer が指すメモリ|空白と有効な形式を確認します。|可|  
|`vswprintf_s`|[swprintf\_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|buffer が指すメモリ|空白と有効な形式を確認します。|no|  
|`_vscprintf`|[\_vscprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|buffer が指すメモリ|null をチェックします。|no|  
|`_vscwprintf`|[\_vscwprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|buffer が指すメモリ|null をチェックします。|no|  
|`_vsnprintf`|[\_snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|buffer が指すメモリ|null をチェックします。|no|  
|`_vsnwprintf`|[\_snwprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|buffer が指すメモリ|null をチェックします。|no|  
  
 `argptr` 引数に VARARGS.H と STDARG.H.で定義されている型 `va_list`があります。  `argptr` の変数は **va\_start,** によって初期化されなければなり、`va_arg` の以降の呼び出しによって再初期化される場合があります。; `argptr` は *format 引数* の対応する仕様に従って出力に変換され、送信された引数リストの先頭をポイントするようになります。  *形式に*[printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)関数の format と同じフォームと関数があります。  これらの関数によって `va_end`を呼び出しません。  `vprintf` の各関数の詳細については、前の表に示したように、対応する関数の説明を参照してください。  
  
 `_vsnprintf` は **vsprintf** の *バッファー*に *バイト数* より多いを記述することです。  
  
 名前の **w** の挿入辞でこれらの関数の各バージョンは **w** の挿入辞せずに対応する関数のワイド文字バージョンであり、; これらのワイド文字単位の各関数では、*バッファー* と *形式は* ワイド文字列です。  それ以外の場合は、ワイド文字関数は、SBCS の対応する関数と同様に動作します。  
  
 **\_s** と **\_p** のサフィックスが付いているこれらの関数の各バージョンはセキュリティが強化されたバージョンです。  これらのバージョンは無効な書式指定文字が使用されている場合\) 書式指定文字列が整形式でない場合、書式指定文字列を使用すると、例外が生成されます。たとえば。  
  
 **\_p** のサフィックスが付いているこれらの関数のバージョンが、指定された書式指定文字列で引数を使用する順序を指定できます。  詳細については、「[printf\_p の位置指定パラメーター](../c-runtime-library/printf-p-positional-parameters.md)」を参照してください。  
  
 **vsprintf**、`vswprintf`、`_vsnprintf` と `_vsnwprintf`用にコピーが重なり合う文字列間にした場合の動作は未定義です。  
  
> [!IMPORTANT]
>  format にユーザー定義の文字列を指定します。  詳細については、「[Avoiding Buffer Overruns](http://msdn.microsoft.com/library/windows/desktop/ms717795)」を参照してください。  これらの関数のセキュリティが強化されたバージョンを使用する場合は **\_s** \(または **\_p** サフィックス\)、ユーザー指定の書式指定文字列は、ユーザーが指定した文字列に無効な書式指定文字が含まれている場合は無効なパラメーターの例外を生成する可能性があります。  
  
## 参照  
 [ストリーム入出力](../c-runtime-library/stream-i-o.md)   
 [fprintf、\_fprintf\_l、fwprintf、\_fwprintf\_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf、\_printf\_l、wprintf、\_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf、\_sprintf\_l、swprintf、\_swprintf\_l、\_\_swprintf\_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg、va\_copy、va\_end、va\_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)