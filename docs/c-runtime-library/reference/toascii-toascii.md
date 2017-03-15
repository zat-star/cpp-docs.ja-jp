---
title: "toascii _ _toascii | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__toascii"
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
  - "__toascii"
  - "toascii"
  - "ctype/toascii"
  - "ctype/__toascii"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "toascii 関数"
  - "ASCII 文字の文字列変換"
  - "__toascii 関数"
  - "ASCII 文字に変換します。"
ms.assetid: a07c0608-b0e2-4da2-a20c-7b64d6a9b77c
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# toascii _ _toascii
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

切り捨てによる文字を 7 ビット ASCII に変換します。  
  
## 構文  
  
```  
int __toascii(  
   int c   
);  
#define toascii __toascii  
```  
  
#### パラメーター  
 `c`  
 変換する文字。  
  
## 戻り値  
 `__toascii` 値に変換 `c` を 7 ビット ASCII の範囲し、結果を返します。 エラーを示すために予約されている戻り値はありません。  
  
## 解説  
 `__toascii` ルーチンを下位 7 ビットを切り捨ててに特定の文字を ASCII 文字に変換します。 その他の変換は適用されません。  
  
 `__toascii` ルーチンはプリプロセッサ マクロ \_CTYPE\_DISABLE\_MACROS が定義されていない場合、マクロとして定義します。 旧バージョンとの互換性のため `toascii` はマクロとして定義される場合にのみ [\_ \_stdc \_ \_](../../preprocessor/predefined-macros.md) が定義されていないか 0; として定義されてそれ以外の場合に未定義です。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`toascii`, `__toascii`|C: \< ctype.h \><br /><br /> C\+\+ の場合: \< cctype \> または \< ctype.h \>|  
  
 `toascii` マクロは、POSIX の拡張機能と `__toascii` は POSIX の拡張機能の Microsoft 固有の実装です。 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)   
 [to 系関数](../../c-runtime-library/to-functions.md)