---
title: "_ultoa、_ultow | Microsoft Docs"
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
  - "_ultoa"
  - "_ultow"
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
  - "ultot"
  - "ultow"
  - "_ultoa"
  - "_ultow"
  - "_ultot"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ultoa 関数"
  - "_ultot 関数"
  - "_ultow 関数"
  - "変換 (整数を)"
  - "変換 (数値の), 文字列への"
  - "整数, 変換"
  - "ultot 関数"
  - "ultow 関数"
ms.assetid: 7a472dc4-5652-4513-93c3-3358522c23be
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ultoa、_ultow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`unsigned long` 型の整数を文字列に変換します。  これらの関数のセキュリティを強化したバージョンについては、「[\_ultoa\_s、\_ultow\_s](../Topic/_ultoa_s,%20_ultow_s.md)」を参照してください。  
  
## 構文  
  
```  
char *_ultoa(  
   unsigned long value,  
   char *str,  
   int radix   
);  
wchar_t *_ultow(  
   unsigned long value,  
   wchar_t *str,  
   int radix   
);  
template <size_t size>  
char *_ultoa(  
   unsigned long value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t *_ultow(  
   unsigned long value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
```  
  
#### パラメーター  
 `value`  
 変換される数値。  
  
 `str`  
 結果の文字列。  
  
 `radix`  
 `value`のベース*。*  
  
## 戻り値  
 これらの各関数は、`str` へのポインターを返します。  エラーの戻り値はありません。  
  
## 解説  
 `_ultoa` 関数は null で終わるな文字列に `value` を変換し、`str`で結果 \(最大 33 バイト\) を格納します。  オーバーフロー チェックは実行されません。  `radix` は `value`のベースを指定します; `radix` は、範囲 2 – 36 にする必要があります。  `_ultow` 関数は、`_ultoa` 関数のワイド文字バージョンです。  
  
> [!IMPORTANT]
>  後続 null 文字に変換された値を保持するには `str` バッファーのサイズが十分であることを、バッファー オーバーランを防ぐには、確認します。  
  
 C\+\+ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_ultot`|`_ultoa`|`_ultoa`|`_ultow`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_ultoa`|\<stdlib.h\>|  
|`_ultow`|\<stdlib.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 [\_itoa](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)"の例を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [\_itoa、\_i64toa、\_ui64toa、\_itow、\_i64tow、\_ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)