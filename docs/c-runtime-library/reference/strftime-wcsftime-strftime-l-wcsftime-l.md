---
title: "strftime、wcsftime、_strftime_l、_wcsftime_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- strftime
- _wcsftime_l
- _strftime_l
- wcsftime
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tcsftime
- strftime
- wcsftime
dev_langs:
- C++
helpviewer_keywords:
- _strftime_l function
- strftime function
- tcsftime function
- _wcsftime_l function
- wcsftime function
- _tcsftime function
- time strings
ms.assetid: 6330ff20-4729-4c4a-82af-932915d893ea
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 1a5331b77e218c5fe5796b2df6d0f61578657758
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="strftime-wcsftime-strftimel-wcsftimel"></a>strftime、wcsftime、_strftime_l、_wcsftime_l
時刻の文字列の書式を指定します。  
  
## <a name="syntax"></a>構文  
  
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
  
#### <a name="parameters"></a>パラメーター  
 `strDest`  
 出力する文字列。  
  
 `maxsize`  
 `strDest` バッファーのサイズ。文字数 (`char` や `wchart_t`) で測定されます。  
  
 `format`  
 書式指定文字列。  
  
 `timeptr`  
 `tm` データ構造。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 `strftime` は `strDest` 内の文字数を返し、`wcsftime` は対応するワイド文字数を返します。  
  
 終端の NULL を含む文字数の合計が `maxsize` を超える場合、`strftime` と `wcsftime` の両方が 0 を返し、`strDest` の内容は不確定です。  
  
 `strDest` 内の文字数は、`format` 内のリテラル文字数と、書式コードを使用して `format` に追加される可能性がある文字数に等しくなります。 文字列の終端の NULL は戻り値にはカウントされません。  
  
## <a name="remarks"></a>コメント  
 `strftime`と`wcsftime`関数形式、`tm`時刻の値`timeptr`に従って、指定された`format`引数と、バッファー内の結果ストア`strDest`です。 文字列には最大 `maxsize` 文字を含めることができます。 `timeptr` 構造のフィールドについては、「[asctime](../../c-runtime-library/reference/asctime-wasctime.md)」をご覧ください。 `wcsftime` は `strftime` のワイド文字版です。その文字列ポインター引数はワイド文字の文字列を指します。 それ以外では、これらの関数の動作は同じです。  
  
> [!NOTE]
>  Visual C++ 2005 より前のバージョンでは、`wcsftime` の `format` パラメーターがデータ型 `const wchar_t *` としてドキュメントに説明されていましたが、実際に実装された `format` データ型は `const char *` でした。 実装、`format`データ型が、現在と以前のドキュメント「、を反映するように更新された`const wchar_t *`です。  
  
 この関数は、パラメーターを検証します。 場合`strDest`、 `format`、または`timeptr`null ポインターでは、または、`tm`によってアドレス指定されるデータ構造体`timeptr`が正しくありません (たとえば、日付や時刻の値が範囲外にある場合)、または、`format`文字列に無効な書式設定コードが含まれている場合、無効なパラメーター ハンドラーが呼び出されます」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、この関数は 0 を返し、`errno` を `EINVAL` に設定します。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsftime`|`strftime`|`strftime`|`wcsftime`|  
  
 `format` 引数は 1 つ以上のコードで構成されます。`printf` と同じように、書式コードの前にはパーセント記号 (`%`) を指定します。 文字で始まらないが`%`をそのままコピーされる`strDest`です。 現在のロケールの `LC_TIME` カテゴリは、`strftime` の出力の書式に影響します。 (`LC_TIME` の詳細については、「[setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」をご覧ください。)`_l` サフィックスが付いていない関数では、現在設定されているロケールを使用します。 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在設定されているロケールの代わりに、ロケールをパラメーターとして使用する点を除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 `strftime` の書式コードを以下に示します。  
  
 `%a`  
 曜日の略称  
  
 `%A`  
 曜日の正式な名前  
  
 `%b`  
 月の略称  
  
 `%B`  
 月の正式な名前  
  
 `%c`  
 ロケールに合った日付と時刻の表記  
  
 `%d`  
 10 進数 (01 ~ 31) で月の日  
  
 `%H`  
 24 時間形式で表される時間 (00 ~ 23)  
  
 `%I`  
 12 時間形式 (01 ~ 12)  
  
 `%j`  
 10 進数 (001 ~ 366) の年の日付  
  
 `%m`  
 10 進数 (01 ~ 12)  
  
 `%M`  
 10 進数による分 (00 ~ 59)  
  
 `%p`  
 現在のロケールのです。 12 時間制のインジケーター  
  
 `%S`  
 10 進数による秒 (00 ~ 59)  
  
 `%U`  
 日曜日を週の最初の日として、10 進数、年間の週 (00 ~ 53)  
  
 `%w`  
 10 進数による曜日 (0 ~ 6 です。日曜日は 0)  
  
 `%W`  
 月曜が週の最初の日の 10 進数で、年の週 (00 ~ 53)  
  
 `%x`  
 現在のロケールの日付表記  
  
 `%X`  
 現在のロケールの時刻表記  
  
 `%y`  
 10 進数として、2 桁の年年 (00 ~ 99)  
  
 `%Y`  
 世紀を付けた 10 進数の年  
  
 `%z, %Z`  
 レジストリ設定に応じて、タイム ゾーンの名前またはタイム ゾーンの略称のいずれか。タイム ゾーンが不明の場合は文字なし  
  
 `%%`  
 パーセント記号  
  
 `printf` 関数と同じように、書式コードのプレフィックスとして `#` フラグを付けることができます。 その場合、書式コードの説明は次のように変更します。  
  
|[書式コード]|説明|  
|-----------------|-------------|  
|`%#a, %#A, %#b, %#B, %#p, %#X, %#z, %#Z, %#%`|`#` フラグは無視されます。|  
|`%#c`|現在のロケールに合った、長い日付と時刻の表記。 たとえば、"Tuesday, March 14, 1995, 12:41:29" です。|  
|`%#x`|現在のロケールに合った、長い日付の表記。 たとえば、"Tuesday, March 14, 1995" です。|  
|`%#d, %#H, %#I, %#j, %#m, %#M, %#S, %#U, %#w, %#W, %#y, %#Y`|先頭にゼロがある場合は削除します。|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`strftime`|\<time.h>|  
|`wcsftime`|\<time.h> または \<wchar.h>|  
|`_strftime_l`|\<time.h>|  
|`_wcsftime_l`|\<time.h> または \<wchar.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
 [time](../../c-runtime-library/reference/time-time32-time64.md) の例を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [ロケール](../../c-runtime-library/locale.md)   
 [時間管理](../../c-runtime-library/time-management.md)   
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcoll 系関数](../../c-runtime-library/strcoll-functions.md)   
 [strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)
