---
title: "strftime、wcsftime、_strftime_l、_wcsftime_l | Microsoft Docs"
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
  - "strftime"
  - "_wcsftime_l"
  - "_strftime_l"
  - "wcsftime"
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
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tcsftime"
  - "strftime"
  - "wcsftime"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_strftime_l 関数"
  - "strftime 関数"
  - "tcsftime 関数"
  - "_wcsftime_l 関数"
  - "wcsftime 関数"
  - "_tcsftime 関数"
  - "時間の文字列"
ms.assetid: 6330ff20-4729-4c4a-82af-932915d893ea
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strftime、wcsftime、_strftime_l、_wcsftime_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

時刻文字列を書式化します。  
  
## 構文  
  
```  
size_t strftime(  
   char *strDest,  
   size_t maxsize,  
   const char *format,  
   const struct tm *timeptr   
);  
size_t _strftime_l(  
   char *strDest,  
   size_t maxsize,  
   const char *format,  
   const struct tm *timeptr,  
   _locale_t locale  
);  
size_t wcsftime(  
   wchar_t *strDest,  
   size_t maxsize,  
   const wchar_t *format,  
   const struct tm *timeptr   
);  
size_t _wcsftime_l(  
   wchar_t *strDest,  
   size_t maxsize,  
   const wchar_t *format,  
   const struct tm *timeptr,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `strDest`  
 出力する文字列。  
  
 `maxsize`  
 文字が使用されます `strDest` バッファーのサイズ \(`char` または `wchart_t`\)。  
  
 `format`  
 書式指定文字列。  
  
 `timeptr`  
 `tm` の データ構造。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 `strftime` は `strDest` に配置された文字数を返します `wcsftime` はワイド文字の対応する番号を返します。  
  
 文字数が、終端の null を含む\) の数より多い場合は、`maxsize``strftime` と `wcsftime` 0 の両方を返し、`strDest` の内容は不確定です。  
  
 `strDest` の文字数が書式指定コードによって `format` に追加できる `format` リテラル文字、文字の数と同じになります。  文字列の終端の null は戻り値としてカウントされます。  
  
## 解説  
 `strftime` と `wcsftime` 関数は `format` の指定された引数に従って `timeptr` の `tm` の時刻の値の書式を指定して、buffer `strDest`に結果を保存します*。*最大でも `maxsize` の文字が文字列内に挿入されます。  `timeptr` 構造体のフィールドの詳細については、「[asctime](../../c-runtime-library/reference/asctime-wasctime.md)」を参照してください。  `wcsftime` は `strftime`のワイド文字単位の等価です; ワイド文字列へのアクセス文字列ポインター引数のポイント。  それ以外では、これらの関数の動作は同じです。  
  
> [!NOTE]
>  Visual C\+\+ 2005 以前のバージョンでは、ドキュメントが記述されていますが `const wchar_t *`データ型を持つとして `wcsftime` の `format` パラメーターを、`format` のデータ型の実際の実装は `const char *`でした。  `format`のデータ型の実装は前と現在のドキュメント、つまり `const wchar_t *`を反映するように更新されました。  
  
 この関数は、パラメーターを検証します。  `strDest`、`format`、または`timeptr` が null ポインターの場合、または `timeptr` して対処する `tm` のデータ構造が無効 \(たとえば、時間または日付の範囲内の値を含む場合、\) である場合は `format` の文字列に無効な書式指定コードが含まれる場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の継続が許可された場合、この関数は 0 を返し、`errno` を `EINVAL` に設定します。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tcsftime`|`strftime`|`strftime`|`wcsftime`|  
  
 `format` の引数は一つ以上のコードで構成されます。; `printf`と同様に、書式指定コードがパーセント記号 \(`%`\) が付きます。  `%` という文字が `strDest`にコピーされます*。*現在のロケールの `LC_TIME` のカテゴリは `strftime`の出力書式に影響します。\(`LC_TIME`の詳細については、「[setlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。`_l` サフィックスのない関数は、現在設定されているロケールを使用します。  `_l` のサフィックスが付いているこれらの関数の各バージョンは同じですが、ロケールをパラメーターとして受け取り、現在設定されているロケールの代わりに使用します。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 `strftime` の書式指定コードを次に示します。:  
  
 `%a`  
 曜日の名前  
  
 `%A`  
 曜日の正式名  
  
 `%b`  
 省略された月名  
  
 `%B`  
 完全な月名  
  
 `%c`  
 ロケールの適切な日付と時刻の表現  
  
 `%d`  
 10 進数 \(01 – 31\) として月の日  
  
 `%H`  
 24 時間制 \(00 – 23 時間\)  
  
 `%I`  
 12 時間制 \(01 – 12 時間\)  
  
 `%j`  
 10 進数 \(001\) として– 366 年の日  
  
 `%m`  
 10 進数 \(01 – 12\) として月  
  
 `%M`  
 10 進数 \(00\) として– 59 分  
  
 `%p`  
 12 時間制の現在のロケールの午前\/アフリカーンス語.のインジケーター  
  
 `%S`  
 second として 10 進数 \(00 – 59\)  
  
 `%U`  
 最初に曜日 \(00 – 53\) の日付として Sunday の 10 進数として年の週、  
  
 `%w`  
 10 進数 \(0 – 6 として Weekday; 日曜日は 0\)  
  
 `%W`  
 最初に曜日 \(00 – 53\) の日付として Monday の 10 進数として年の週、  
  
 `%x`  
 現在のロケールの日付の表現  
  
 `%X`  
 現在のロケールの時刻の表現  
  
 `%y`  
 10 進数 \(00 – 99\) として世紀のではなく、  
  
 `%Y`  
 10 進数として世紀の年、  
  
 `%z, %Z`  
 レジストリの設定によって、タイム ゾーンの名前またはタイム ゾーンの省略形、; タイム ゾーンが不明な場合は文字なし  
  
 `%%`  
 パーセント記号  
  
 `printf` 関数と同様に、`#` フラグは書式指定コードを付け加える場合があります。  この場合、書式指定コードの意味は、次のように変更されます。  
  
|\[書式コード\]|説明|  
|---------------|--------|  
|`%#a, %#A, %#b, %#B, %#p, %#X, %#z, %#Z, %#%`|`#` フラグは無視されます。|  
|`%#c`|長い日付と時刻の表現は現在のロケールでは、割り当てます。  例: 「Tuesday November 1995 \(3 年 12 月 14 日 12:41: 29 "です。|  
|`%#x`|長い日付形式は現在のロケールに、割り当てます。  例: 「Tuesday November 1995 \(3 年 12 月 14 日」。|  
|`%#d, %#H, %#I, %#j, %#m, %#M, %#S, %#U, %#w, %#W, %#y, %#Y`|先行するゼロを削除します \(存在する場合\)。|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`strftime`|\<time.h\>|  
|`wcsftime`|\<time.h または\> wchar.h \<\>|  
|`_strftime_l`|\<time.h\>|  
|`_wcsftime_l`|\<time.h または\> wchar.h \<\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 「[time](../Topic/time,%20_time32,%20_time64.md)」の例を参照してください。  
  
## 同等の .NET Framework 関数  
  
-   [System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
## 参照  
 [ロケール](../../c-runtime-library/locale.md)   
 [時間管理](../../c-runtime-library/time-management.md)   
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [strcoll 系関数](../../c-runtime-library/strcoll-functions.md)   
 [strxfrm、wcsxfrm、\_strxfrm\_l、\_wcsxfrm\_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)