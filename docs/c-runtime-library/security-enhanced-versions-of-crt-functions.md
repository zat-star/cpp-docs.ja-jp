---
title: "CRT 関数のセキュリティが強化されたバージョン | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "CRT, セキュリティ強化"
  - "セキュリティ [CRT]"
  - "セキュリティ強化 CRT"
ms.assetid: f87e5a01-4cb2-4379-9e8f-d4693828c55a
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# CRT 関数のセキュリティが強化されたバージョン
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

セキュリティが強化されたバージョンのランタイム ライブラリ ルーチンを利用できます。 CRT のセキュリティ強化について詳しくは、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」をご覧ください。  
  
 **セキュリティで保護された関数**  
  
|CRT 関数|セキュリティが強化された関数|使用|  
|------------|--------------------|--------|  
|[\_access、\_waccess](../c-runtime-library/reference/access-waccess.md)|[\_access\_s、\_waccess\_s](../c-runtime-library/reference/access-s-waccess-s.md)|ファイル アクセス許可を決定します。|  
|[\_alloca](../c-runtime-library/reference/alloca.md)|[\_malloca](../c-runtime-library/reference/malloca.md)|スタックにメモリを割り当てます。|  
|[asctime、\_wasctime](../c-runtime-library/reference/asctime-wasctime.md)|[asctime\_s、\_wasctime\_s](../c-runtime-library/reference/asctime-s-wasctime-s.md)|時刻を `struct tm` 型から文字列に変換します。|  
|[bsearch](../c-runtime-library/reference/bsearch.md)|[bsearch\_s](../c-runtime-library/reference/bsearch-s.md)|並べ替えられた配列のバイナリ検索を実行します。|  
|古い関数|[\_cgets\_s、\_cgetws\_s](../Topic/_cgets_s,%20_cgetws_s.md)|コンソールから文字列を取得します。|  
|[\_chsize](../c-runtime-library/reference/chsize.md)|[\_chsize\_s](../c-runtime-library/reference/chsize-s.md)|ファイル サイズを変更します。|  
|[clearerr](../c-runtime-library/reference/clearerr.md)|[clearerr\_s](../c-runtime-library/reference/clearerr-s.md)|ストリームのエラー インジケーターをリセットします。|  
|[\_control87、\_controlfp、\_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md)|[\_controlfp\_s](../c-runtime-library/reference/controlfp-s.md)|浮動小数点制御ワードの取得および設定を行います。|  
|[\_cprintf、\_cprintf\_l、\_cwprintf、\_cwprintf\_l](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|[\_cprintf\_s、\_cprintf\_s\_l、\_cwprintf\_s、\_cwprintf\_s\_l](../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)|書式化してコンソールに出力します。|  
|[\_cscanf、\_cscanf\_l、\_cwscanf、\_cwscanf\_l](../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)|[\_cscanf\_s、\_cscanf\_s\_l、\_cwscanf\_s、\_cwscanf\_s\_l](../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)|書式付きデータをコンソールから読み取ります。|  
|[ctime、\_ctime32、\_ctime64、\_wctime、\_wctime32、\_wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)|[\_ctime\_s、\_ctime32\_s、\_ctime64\_s、\_wctime\_s、\_wctime32\_s、\_wctime64\_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)|時刻を `time_t` 型、`__time32_t` 型、または `__time64_t` 型から文字列に変換します。|  
|[\_ecvt](../c-runtime-library/reference/ecvt.md)|[\_ecvt\_s](../Topic/_ecvt_s.md)|`double` の数値を文字列に変換します。|  
|[\_fcvt](../Topic/_fcvt.md)|[\_fcvt\_s](../c-runtime-library/reference/fcvt-s.md)|浮動小数点数を文字列に変換します。|  
|[fopen、\_wfopen](../c-runtime-library/reference/fopen-wfopen.md)|[fopen\_s、\_wfopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)|ファイルを開きます。|  
|[fprintf、\_fprintf\_l、fwprintf、\_fwprintf\_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[fprintf\_s、\_fprintf\_s\_l、fwprintf\_s、\_fwprintf\_s\_l](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|書式付きデータをストリームに出力します。|  
|[fread](../c-runtime-library/reference/fread.md)|[fread\_s](../c-runtime-library/reference/fread-s.md)|ファイルのデータを読み取ります。|  
|[\_fread\_nolock](../c-runtime-library/reference/fread-nolock.md)|[\_fread\_nolock\_s](../Topic/_fread_nolock_s2.md)|マルチスレッドの書き込みロックを使用せずに、ファイルから読み取ります。|  
|[freopen、\_wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)|[freopen\_s、\_wfreopen\_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md)|ファイルをもう一度開きます。|  
|[fscanf、\_fscanf\_l、fwscanf、\_fwscanf\_l](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[fscanf\_s、\_fscanf\_s\_l、fwscanf\_s、\_fwscanf\_s\_l](../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)|書式付きデータをストリームから読み出します。|  
|[\_ftime、\_ftime32、\_ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md)|[\_ftime\_s、\_ftime32\_s、\_ftime64\_s](../Topic/_ftime_s,%20_ftime32_s,%20_ftime64_s.md)|現在の時刻を取得します。|  
|[\_gcvt](../c-runtime-library/reference/gcvt.md)|[\_gcvt\_s](../c-runtime-library/reference/gcvt-s.md)|浮動小数点値を文字列に変換し、バッファーに格納します。|  
|[getenv、\_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)|[getenv\_s、\_wgetenv\_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)|現在の環境から値を取得します。|  
|古い関数|[gets\_s、\_getws\_s](../c-runtime-library/reference/gets-s-getws-s.md)|`stdin` ストリームから行を取得します。|  
|[gmtime、\_gmtime32、\_gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)|[\_gmtime32\_s、\_gmtime64\_s](../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)|時刻を `time_t` 型から `struct``tm` に変換するか、`__time64_t` 型から `struct tm` に変換します。|  
|[\_itoa、\_i64toa、\_ui64toa、\_itow、\_i64tow、\_ui64tow](../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)|[\_itoa\_s、\_i64toa\_s、\_ui64toa\_s、\_itow\_s、\_i64tow\_s、\_ui64tow\_s](../c-runtime-library/reference/itoa-s-i64toa-s-ui64toa-s-itow-s-i64tow-s-ui64tow-s.md)|整数を文字列に変換します。|  
|[\_lfind](../c-runtime-library/reference/lfind.md)|[\_lfind\_s](../Topic/_lfind_s.md)|指定されたキーの線形探索を実行します。|  
|[localtime、\_localtime32、\_localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md)|[localtime\_s、\_localtime32\_s、\_localtime64\_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)|時刻を `time_t` 型から `struct tm` に変換するか、`__time64_t` 型からローカル時刻に修正した `struct tm`に変換します。|  
|[\_lsearch](../c-runtime-library/reference/lsearch.md)|[\_lsearch\_s](../c-runtime-library/reference/lsearch-s.md)|ある値に関して線形探索を実行し、見つからない場合はリストの末尾に追加します。|  
|[\_ltoa、\_ltow](../Topic/_ltoa,%20_ltow.md)|[\_ltoa\_s、\_ltow\_s](../c-runtime-library/reference/ltoa-s-ltow-s.md)|長整数型を文字列に変換します。|  
|[\_makepath、\_wmakepath](../c-runtime-library/reference/makepath-wmakepath.md)|[\_makepath\_s、\_wmakepath\_s](../c-runtime-library/reference/makepath-s-wmakepath-s.md)|コンポーネントからパス名を作成します。|  
|[\_mbccpy、\_mbccpy\_l](../Topic/_mbccpy,%20_mbccpy_l.md)|[\_mbccpy\_s、\_mbccpy\_s\_l](../c-runtime-library/reference/mbccpy-s-mbccpy-s-l.md)|マルチバイト文字を文字列から別の文字列にコピーします。|  
|[\_mbsnbcat、\_mbsnbcat\_l](../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)|[\_mbsnbcat\_s、\_mbsnbcat\_s\_l](../Topic/_mbsnbcat_s,%20_mbsnbcat_s_l.md)|1 つのマルチバイト文字列の先頭の最大 `n` バイトを別の文字列に追加します。|  
|[\_mbsnbcpy、\_mbsnbcpy\_l](../Topic/_mbsnbcpy,%20_mbsnbcpy_l.md)|[\_mbsnbcpy\_s、\_mbsnbcpy\_s\_l](../c-runtime-library/reference/mbsnbcpy-s-mbsnbcpy-s-l.md)|文字列の `n` バイトを宛先文字列にコピーします。|  
|[\_mbsnbset、\_mbsnbset\_l](../c-runtime-library/reference/mbsnbset-mbsnbset-l.md)|[\_mbsnbset\_s、\_mbsnbset\_s\_l](../c-runtime-library/reference/mbsnbset-s-mbsnbset-s-l.md)|文字列の最初の `n` バイトを、指定された文字に設定します。|  
|[mbsrtowcs](../c-runtime-library/reference/mbsrtowcs.md)|[mbsrtowcs\_s](../c-runtime-library/reference/mbsrtowcs-s.md)|マルチバイト文字の文字列を対応するワイド文字の文字列に変換します。|  
|[mbstowcs、\_mbstowcs\_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)|[mbstowcs\_s、\_mbstowcs\_s\_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|マルチバイト文字のシーケンスを、対応するワイド文字のシーケンスに変換します。|  
|[memcpy、wmemcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)|[memcpy\_s、wmemcpy\_s](../c-runtime-library/reference/memcpy-s-wmemcpy-s.md)|バッファー間で文字をコピーします。|  
|[memmove、wmemmove](../c-runtime-library/reference/memmove-wmemmove.md)|[memmove\_s、wmemmove\_s](../c-runtime-library/reference/memmove-s-wmemmove-s.md)|バッファーを別のバッファーに移動します。|  
|[\_mktemp、\_wmktemp](../c-runtime-library/reference/mktemp-wmktemp.md)|[\_mktemp\_s、\_wmktemp\_s](../c-runtime-library/reference/mktemp-s-wmktemp-s.md)|一意のファイル名を作成します。|  
|[printf、\_printf\_l、wprintf、\_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|[printf\_s、\_printf\_s\_l、wprintf\_s、\_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|標準出力ストリームに書式付きで出力します。|  
|[\_putenv、\_wputenv](../c-runtime-library/reference/putenv-wputenv.md)|[\_putenv\_s、\_wputenv\_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)|環境変数を作成、変更、または削除します。|  
|[qsort](../c-runtime-library/reference/qsort.md)|[qsort\_s](../c-runtime-library/reference/qsort-s.md)|クイック ソートを実行します。|  
|[rand](../Topic/rand.md)|[rand\_s](../c-runtime-library/reference/rand-s.md)|疑似乱数を生成します。|  
|[scanf、\_scanf\_l、wscanf、\_wscanf\_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)|[scanf\_s、\_scanf\_s\_l、wscanf\_s、\_wscanf\_s\_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)|標準入力ストリームから書式付きデータを読み出します。|  
|[\_searchenv、\_wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md)|[\_searchenv\_s、\_wsearchenv\_s](../Topic/_searchenv_s,%20_wsearchenv_s.md)|環境パスを使用してファイルを検索します。|  
|[snprintf、\_snprintf、\_snprintf\_l、\_snwprintf、\_snwprintf\_l](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|[\_snprintf\_s、\_snprintf\_s\_l、\_snwprintf\_s、\_snwprintf\_s\_l](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)|文字列に書式付きデータを書き込みます。|  
|[\_snscanf、\_snscanf\_l、\_snwscanf、\_snwscanf\_l](../c-runtime-library/reference/snscanf-snscanf-l-snwscanf-snwscanf-l.md)|[\_snscanf\_s、\_snscanf\_s\_l、\_snwscanf\_s、\_snwscanf\_s\_l](../c-runtime-library/reference/snscanf-s-snscanf-s-l-snwscanf-s-snwscanf-s-l.md)|指定した長さの書式付きデータを文字列から読み出します。|  
|[\_sopen、\_wsopen](../c-runtime-library/reference/sopen-wsopen.md)|[\_sopen\_s、\_wsopen\_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|共有用にファイルを開きます。|  
|[\_splitpath、\_wsplitpath](../Topic/_splitpath,%20_wsplitpath.md)|[\_splitpath\_s、\_wsplitpath\_s](../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)|パス名をコンポーネントに分割します。|  
|[sprintf、\_sprintf\_l、swprintf、\_swprintf\_l、\_\_swprintf\_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|[sprintf\_s、\_sprintf\_s\_l、swprintf\_s、\_swprintf\_s\_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|文字列に書式付きデータを書き込みます。|  
|[sscanf、\_sscanf\_l、swscanf、\_swscanf\_l](../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)|[sscanf\_s、\_sscanf\_s\_l、swscanf\_s、\_swscanf\_s\_l](../Topic/sscanf_s,%20_sscanf_s_l,%20swscanf_s,%20_swscanf_s_l.md)|文字列から書式付きデータを読み出します。|  
|[strcat、wcscat、\_mbscat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)|[strcat\_s、wcscat\_s、\_mbscat\_s](../c-runtime-library/reference/strcat-s-wcscat-s-mbscat-s.md)|文字列を追加します。|  
|[strcpy、wcscpy、\_mbscpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|[strcpy\_s、wcscpy\_s、\_mbscpy\_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)|文字列をコピーします。|  
|[\_strdate、\_wstrdate](../c-runtime-library/reference/strdate-wstrdate.md)|[\_strdate\_s、\_wstrdate\_s](../c-runtime-library/reference/strdate-s-wstrdate-s.md)|現在のシステム日付を文字列として返します。|  
|[strerror、\_strerror、\_wcserror、\_\_wcserror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)|[strerror\_s、\_strerror\_s、\_wcserror\_s、\_\_wcserror\_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)|システム エラー メッセージ \(`strerror`、`_wcserror`\) を取得します。または、ユーザーが指定したエラー メッセージ \(`_strerror`、`__wcserror`\) を出力します。|  
|[\_strlwr、\_wcslwr、\_mbslwr、\_strlwr\_l、\_wcslwr\_l、\_mbslwr\_l](../Topic/_strlwr,%20_wcslwr,%20_mbslwr,%20_strlwr_l,%20_wcslwr_l,%20_mbslwr_l.md)|[\_strlwr\_s、\_strlwr\_s\_l、\_mbslwr\_s、\_mbslwr\_s\_l、\_wcslwr\_s、\_wcslwr\_s\_l](../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md)|文字列を小文字に変換します。|  
|[strncat、\_strncat\_l、wcsncat、\_wcsncat\_l、\_mbsncat、\_mbsncat\_l](../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|[strncat\_s、\_strncat\_s\_l、wcsncat\_s、\_wcsncat\_s\_l、\_mbsncat\_s、\_mbsncat\_s\_l](../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)|文字列に文字を追加します。|  
|[strncpy、\_strncpy\_l、wcsncpy、\_wcsncpy\_l、\_mbsncpy、\_mbsncpy\_l](../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)|[strncpy\_s、\_strncpy\_s\_l、wcsncpy\_s、\_wcsncpy\_s\_l、\_mbsncpy\_s、\_mbsncpy\_s\_l](../Topic/strncpy_s,%20_strncpy_s_l,%20wcsncpy_s,%20_wcsncpy_s_l,%20_mbsncpy_s,%20_mbsncpy_s_l.md)|1 つの文字列の文字を別の文字列にコピーします。|  
|[\_strnset、\_strnset\_l、\_wcsnset、\_wcsnset\_l、\_mbsnset、\_mbsnset\_l](../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)|[\_strnset\_s、\_strnset\_s\_l、\_wcsnset\_s、\_wcsnset\_s\_l、\_mbsnset\_s、\_mbsnset\_s\_l](../c-runtime-library/reference/strnset-s-strnset-s-l-wcsnset-s-wcsnset-s-l-mbsnset-s-mbsnset-s-l.md)|文字列の最初の n 文字を、指定された文字に設定します。|  
|[\_strset、\_strset\_l、\_wcsset、\_wcsset\_l、\_mbsset、\_mbsset\_l](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|[\_strset\_s、\_wcsset\_s、\_wcsset\_s\_l、\_mbsset\_s、\_mbsset\_s\_l](../Topic/_strset_s,%20_strset_s_l,%20_wcsset_s,%20_wcsset_s_l,%20_mbsset_s,%20_mbsset_s_l.md)|文字列のすべての文字を、指定された文字に設定します。|  
|[\_strtime、\_wstrtime](../Topic/_strtime,%20_wstrtime.md)|[\_strtime\_s、\_wstrtime\_s](../c-runtime-library/reference/strtime-s-wstrtime-s.md)|現在のシステム時刻を文字列として返します。|  
|[strtok、\_strtok\_l、wcstok、\_wcstok\_l、\_mbstok、\_mbstok\_l](../Topic/strtok,%20_strtok_l,%20wcstok,%20_wcstok_l,%20_mbstok,%20_mbstok_l.md)|[strtok\_s、\_strtok\_s\_l、wcstok\_s、\_wcstok\_s\_l、\_mbstok\_s、\_mbstok\_s\_l](../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md)|現在のロケールまたは渡されたロケールを使用して、文字列内の次のトークンを検索します。|  
|[\_strupr、\_strupr\_l、\_mbsupr、\_mbsupr\_l、\_wcsupr\_l、\_wcsupr](../c-runtime-library/reference/strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md)|[\_strupr\_s、\_strupr\_s\_l、\_mbsupr\_s、\_mbsupr\_s\_l、\_wcsupr\_s、\_wcsupr\_s\_l](../c-runtime-library/reference/strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md)|文字列を大文字に変換します。|  
|[tmpfile](../c-runtime-library/reference/tmpfile.md)|[tmpfile\_s](../Topic/tmpfile_s.md)|一時ファイルを作成します。|  
|[\_tempnam、\_wtempnam、tmpnam、\_wtmpnam](../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|[tmpnam\_s、\_wtmpnam\_s](../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md)|一時ファイルの作成に使用できる名前を生成します。|  
|[\_ultoa、\_ultow](../c-runtime-library/reference/ultoa-ultow.md)|[\_ultoa\_s、\_ultow\_s](../Topic/_ultoa_s,%20_ultow_s.md)|符号なし長整数型を文字列に変換します。|  
|[\_umask](../c-runtime-library/reference/umask.md)|[\_umask\_s](../Topic/_umask_s.md)|既定のファイル アクセス許可マスクを設定します。|  
|[\_vcprintf、\_vcprintf\_l、\_vcwprintf、\_vcwprintf\_l](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md)|[\_vcprintf\_s、\_vcprintf\_s\_l、\_vcwprintf\_s、\_vcwprintf\_s\_l](../c-runtime-library/reference/vcprintf-s-vcprintf-s-l-vcwprintf-s-vcwprintf-s-l.md)|引数リストへのポインターを使用して、書式付き出力をコンソールに書き込みます。|  
|[vfprintf、\_vfprintf\_l、vfwprintf、\_vfwprintf\_l](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|[vfprintf\_s、\_vfprintf\_s\_l、vfwprintf\_s、\_vfwprintf\_s\_l](../Topic/vfprintf_s,%20_vfprintf_s_l,%20vfwprintf_s,%20_vfwprintf_s_l.md)|引数リストへのポインターを使用して、書式付き出力を書き込みます。|  
|[vfscanf、vfwscanf](../c-runtime-library/reference/vfscanf-vfwscanf.md)|[vfscanf\_s、vfwscanf\_s](../c-runtime-library/reference/vfscanf-s-vfwscanf-s.md)|書式付きデータをストリームから読み出します。|  
|[vprintf、\_vprintf\_l、vwprintf、\_vwprintf\_l](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|[vprintf\_s、\_vprintf\_s\_l、vwprintf\_s、\_vwprintf\_s\_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)|引数リストへのポインターを使用して、書式付き出力を書き込みます。|  
|[vscanf、vwscanf](../c-runtime-library/reference/vscanf-vwscanf.md)|[vscanf\_s、vwscanf\_s](../c-runtime-library/reference/vscanf-s-vwscanf-s.md)|標準入力ストリームから書式付きデータを読み出します。|  
|[vsnprintf、\_vsnprintf、\_vsnprintf\_l、\_vsnwprintf、\_vsnwprintf\_l](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md)|[vsnprintf\_s、\_vsnprintf\_s、\_vsnprintf\_s\_l、\_vsnwprintf\_s、\_vsnwprintf\_s\_l](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)|引数リストへのポインターを使用して、書式付き出力を書き込みます。|  
|[vsprintf、\_vsprintf\_l、vswprintf、\_vswprintf\_l、\_\_vswprintf\_l](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)|[vsprintf\_s、\_vsprintf\_s\_l、vswprintf\_s、\_vswprintf\_s\_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)|引数リストへのポインターを使用して、書式付き出力を書き込みます。|  
|[vsscanf、vswscanf](../c-runtime-library/reference/vsscanf-vswscanf.md)|[vsscanf\_s、vswscanf\_s](../c-runtime-library/reference/vsscanf-s-vswscanf-s.md)|文字列から書式付きデータを読み出します。|  
|[wcrtomb](../c-runtime-library/reference/wcrtomb.md)|[wcrtomb\_s](../c-runtime-library/reference/wcrtomb-s.md)|ワイド文字をマルチバイト文字の表現に変換します。|  
|[wcsrtombs](../c-runtime-library/reference/wcsrtombs.md)|[wcsrtombs\_s](../c-runtime-library/reference/wcsrtombs-s.md)|ワイド文字の文字列をマルチバイト文字の文字列表現に変換します。|  
|[wcstombs、\_wcstombs\_l](../Topic/wcstombs,%20_wcstombs_l.md)|[wcstombs\_s、\_wcstombs\_s\_l](../Topic/wcstombs_s,%20_wcstombs_s_l.md)|ワイド文字のシーケンスを、対応するマルチバイト文字のシーケンスに変換します。|  
|[wctomb、\_wctomb\_l](../c-runtime-library/reference/wctomb-wctomb-l.md)|[wctomb\_s、\_wctomb\_s\_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|ワイド文字を対応するマルチバイト文字に変換します。|  
  
## 参照  
 [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)