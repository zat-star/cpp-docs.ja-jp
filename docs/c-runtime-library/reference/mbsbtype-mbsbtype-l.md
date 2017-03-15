---
title: "_mbsbtype、_mbsbtype_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsbtype_l"
  - "_mbsbtype"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "mbsbtype"
  - "mbsbtype_l"
  - "_mbsbtype_l"
  - "_mbsbtype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsbtype 関数"
  - "_mbsbtype_l 関数"
  - "mbsbtype 関数"
  - "mbsbtype_l 関数"
ms.assetid: 0d5dd91a-d32d-4f98-ac57-98dfc9e98eac
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _mbsbtype、_mbsbtype_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列内のバイトの種類を返します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
int _mbsbtype(  
   const unsigned char *mbstr,  
   size_t count   
);  
int _mbsbtype_l(  
   const unsigned char *mbstr,  
   size_t count,  
   _locale_t locale   
);  
```  
  
#### パラメーター  
 `mbstr`  
 マルチバイト文字のシーケンスのアドレス。  
  
 `count`  
 文字列の先頭からのバイト オフセット。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 `_mbsbtype` と `_mbsbtype_l`を示す整数値を指定されたバイトのテストの結果を返します。  次の表のマニフェスト定数は、Mbctype.h で定義されています。  
  
|戻り値|バイトの種類|  
|---------|------------|  
|`_MBC_SINGLE` \(0\)|1 バイト文字。  たとえば、コード ページ 932 では、0x20 ～ 0x7E または 0xA1 ～ 0xDF の範囲のバイトを指定すると、`_mbsbtype` は 0 を返します。|  
|`_MBC_LEAD` \(1\)|マルチバイト文字の先行バイト。  たとえば、コード ページ 932 では、0x81 ～ 0x9F または 0xE0 ～ 0xFC の範囲のバイトを指定すると、`_mbsbtype` は 1 を返します。|  
|`_MBC_TRAIL` \(2\)|マルチバイト文字の後続バイト。  たとえば、コード ページ 932 では、0x40 ～ 0x7E または 0x80 ～ 0xFC の範囲のバイトを指定すると、`_mbsbtype` は 2 を返します。|  
|`_MBC_ILLEGAL` \(–1\)|`mbstr` のオフセット `count` の位置にあるバイトの前に見つかった、`NULL` 文字列、無効な文字、または `NULL` バイト。|  
  
## 解説  
 `_mbsbtype` 関数は、マルチバイト文字列のバイトの種類を判断します。  この関数は、`mbstr` のオフセット `count` の位置にあるバイトだけを調べます。指定されたバイトの前にある無効な文字は無視します。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  `_l` サフィックスが付いていないこの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 入力文字列が `NULL` の場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、`errno` が `EINVAL` に設定され、関数から `_MBC_ILLEGAL` が返されます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|----------|------------|----------------|  
|`_mbsbtype`|\<mbstring.h\>|\<mbctype.h\>\*|  
|`_mbsbtype_l`|\<mbstring.h\>|\<mbctype.h\>\*|  
  
 \* 戻り値として使用されるマニフェスト定数の場合。  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 該当するものはありません。ただし、「[System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)」を参照してください。  
  
## 参照  
 [バイト分類](../../c-runtime-library/byte-classification.md)