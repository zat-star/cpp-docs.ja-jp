---
title: "mbstowcs_s、_mbstowcs_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbstowcs_s_l"
  - "mbstowcs_s"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_mbstowcs_s_l"
  - "mbstowcs_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbstowcs_s_l 関数"
  - "mbstowcs_s 関数"
  - "mbstowcs_s_l 関数"
ms.assetid: 2fbda953-6918-498f-b440-3e7b21ed65a4
caps.latest.revision: 31
caps.handback.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# mbstowcs_s、_mbstowcs_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ワイド文字の対応するシーケンスにマルチバイト文字のシーケンスを変換します。  [CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)"に説明されているように、セキュリティが強化された [mbstowcs、\_mbstowcs\_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md) のバージョン。  
  
## 構文  
  
```  
errno_t mbstowcs_s(  
   size_t *pReturnValue,  
   wchar_t *wcstr,  
   size_t sizeInWords,  
   const char *mbstr,  
   size_t count   
);  
errno_t _mbstowcs_s_l(  
   size_t *pReturnValue,  
   wchar_t *wcstr,  
   size_t sizeInWords,  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t mbstowcs_s(  
   size_t *pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbstowcs_s_l(  
   size_t *pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### パラメーター  
 \[出力\] `pReturnValue`  
 変換された文字数。  
  
 \[出力\] `wcstr`  
 発生する可能性のバッファーのアドレスはワイド文字列を変換します。  
  
 \[入力\] `sizeInWords`  
 Word の `wcstr` バッファーのサイズ。  
  
 \[入力\] `mbstr`  
 null で終わる文字列のマルチバイト文字のシーケンスのアドレス。  
  
 \[入力\] `count`  
 `wcstr` バッファーで、終端の null は含まない格納するワイド文字の最大数を [\_TRUNCATE](../../c-runtime-library/truncate.md)。  
  
 \[入力\] `locale`  
 使用するロケール。  
  
## 戻り値  
 正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。  
  
|エラー条件|戻り値と `errno`|  
|-----------|------------------|  
|`wcstr` は `NULL` と `sizeInWords` \> 0 です。|`EINVAL`|  
|`mbstr` が `NULL` です。|`EINVAL`|  
|変換先バッファーが小さいため変換後の文字列が収まらない \(`count` が `_TRUNCATE` の場合は例外。下記の「解説」を参照\)|`ERANGE`|  
|`wcstr` は `NULL` と `sizeInWords` \=\= 0 ではありません。|`EINVAL`|  
  
 上記のいずれかの条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーターの例外が呼び出されます。  実行の続行が許可された場合、関数はエラー コードを返し、`errno` を表で示されている値に設定します。  
  
## 解説  
 `mbstowcs_s` 関数は `wcstr`が指すバッファーに格納されているワイド文字に `mbstr` が指すマルチバイト文字列に変換します。  変換は各文字列に対して行われ、次の条件の 1 つが満たされるまで続行されます。  
  
-   マルチバイトの null 文字が検出された  
  
-   無効なマルチバイト文字が検出された  
  
-   `wcstr` バッファーに格納されているワイド文字数を `count`になります。  
  
 変換後の文字列は、常に null で終わります \(エラーの場合も同様\)。  
  
 `count` が特殊な値 [\_TRUNCATE](../../c-runtime-library/truncate.md)の場合、`mbstowcs_s` は、null 終端文字の空きを残して変換先バッファーに収まるように文字列と変換を行います。  
  
 `mbstowcs_s` が正常にソース文字列を変換すると、`*``pReturnValue` に変換された文字列のワイド文字単位のサイズを、null 終端文字が送信します \(指定された `pReturnValue` は `NULL`ではありません\)。  これは、`wcstr` 引数が `NULL` の場合でも発生するので、これを使用して必要なバッファー サイズを確認できます。  `wcstr` が `NULL`、`count` は無視され、`sizeInWords` を 0 にすることはできません。  
  
 `mbstowcs_s` に無効なマルチバイト文字があると、`*``pReturnValue`に 0 を配置し、空の文字列に変換先バッファーを設定し、`EILSEQ`に `errno` を設定し、`EILSEQ`を返します。  
  
 `mbstr` と `wcstr` が指す文字列が重なり合う場合、`mbstowcs_s` 関数の動作は未定義です。  
  
> [!IMPORTANT]
>  `wcstr` と `mbstr` が重複しないよう、`count` が変換に正しくマルチバイト文字数を反映していることを確認します。  
  
 `mbstowcs_s` は、すべてのロケールに依存する動作に現在のロケールを使用して; `_mbstowcs_s_l` は同じですが、渡されたロケールを代わりに使用します。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 C\+\+ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる \(サイズの引数を指定する必要がなくなる\) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`mbstowcs_s`|\<stdlib.h\>|  
|`_mbstowcs_s_l`|\<stdlib.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbclen、mblen、\_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbtowc、\_mbtowc\_l](../Topic/mbtowc,%20_mbtowc_l.md)   
 [wcstombs、\_wcstombs\_l](../Topic/wcstombs,%20_wcstombs_l.md)   
 [wctomb、\_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)