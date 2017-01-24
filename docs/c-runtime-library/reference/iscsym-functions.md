---
title: "iscsym、iscsymf、_ _iscsym、_ _iswcsym、_ _iscsymf、_ _iswcsymf、_iscsym_l、_iswcsym_l、_iscsymf_l、_iswcsymf_l | Microsoft Docs"
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
  - "_iswcsym_l"
  - "__iswcsym"
  - "__iscsym"
  - "_iswcsymf_l"
  - "_iscsym_l"
  - "__iswcsymf"
  - "__iscsymf"
  - "_iscsymf_l"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_iswcsym_l"
  - "_iswcsymf_l"
  - "iscsymf"
  - "iswcsymf"
  - "__iswcsym"
  - "__iswcsymf"
  - "iscsym"
  - "iswcsym"
  - "__iscsym"
  - "_iscsym_l"
  - "_iscsymf_l"
  - "__iscsymf"
  - "ctype/iscsym"
  - "ctype/iscsymf"
  - "ctype/__iscsym"
  - "ctype/__iscsymf"
  - "ctype/__iscsym_l"
  - "ctype/__iscsymf_l"
  - "ctype/__iswcsym"
  - "ctype/__iswcsymf"
  - "ctype/__iswcsym_l"
  - "ctype/__iswcsymf_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "iscsymf_l 関数"
  - "iswsym_l 関数"
  - "_iswcsym_l 関数"
  - "iscsym_l 関数"
  - "_iscsymf_l 関数"
  - "_iswcsymf_l 関数"
  - "_iscsym_l 関数"
  - "__iscsym 関数"
  - "__iswcsymf 関数"
  - "iswsymf_l 関数"
  - "__iscsymf 関数"
  - "__iswcsym 関数"
  - "iscsym 関数"
  - "iscsymf 関数"
ms.assetid: 944dfb99-f2b8-498c-9f55-dbcf370d0a2c
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# iscsym、iscsymf、_ _iscsym、_ _iswcsym、_ _iscsymf、_ _iswcsymf、_iscsym_l、_iswcsym_l、_iscsymf_l、_iswcsymf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

整数が識別子に使用できる文字を表すかを決定します。  
  
## 構文  
  
```  
int __iscsym(   
   int c   
);  
int __iswcsym(   
   wint_t c   
);  
int __iscsymf(   
   int c   
);  
int __iswcsymf(   
   wint_t c   
);  
int _iscsym_l(   
   int c,  
   _locale_t locale  
);  
int _iswcsym_l(   
   wint_t c,  
   _locale_t locale  
);  
int _iscsymf_l(   
   int c,  
   _locale_t locale  
);  
int _iswcsymf_l(   
   wint_t c,  
   _locale_t locale  
);  
#define iscsym __iscsym  
#define iscsymf __iscsymf  
```  
  
#### パラメーター  
 `c`  
 テストする整数。`c` 関数のナロー文字のバージョンについては、0 ~ 255 の範囲でなければなりません。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 両方 `__iscsym` と `__iswcsym` 場合は、0 以外の値を返す `c` は文字、アンダー スコア、または数字。 両方とも `__iscsymf` と `__iswcsymf` 場合は、0 以外の値を返す `c` が文字またはアンダー スコア。 これらの各ルーチンは、`c` がテスト条件を満たしていない場合は 0 を返します。 これらの関数のうち `_l` サフィックスが付けられたバージョンは同じですが、ロケールに依存する動作に現在のロケールではなく渡されたロケールを使用するという点で異なります。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
## 解説  
 これらのルーチンは、プリプロセッサ マクロ \_CTYPE\_DISABLE\_MACROS が定義されていない場合、マクロとして定義されます。 これらのルーチンのマクロのバージョンを使用すると、引数を複数回評価できます。 引数リスト内での副作用がある式を使用するときは注意をしてください。  
  
 旧バージョンとの互換性のため `iscsym` と `iscsymf` マクロとして定義される場合にのみ [\_ \_stdc \_ \_](../../preprocessor/predefined-macros.md) が定義されていないか 0; として定義されてそれ以外の場合は未定義です。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`iscsym`、`iscsymf`、`__iscsym`、`__iswcsym`、`__iscsymf`、`__iswcsymf`、`_iscsym_l`、`_iswcsym_l`、`_iscsymf_l`、`_iswcsymf_l`|C: \< ctype.h \><br /><br /> C\+\+ の場合: \< cctype \> または \< ctype.h \>|  
  
 `iscsym`, 、`iscsymf`, 、`__iscsym`, 、`__iswcsym`, 、`__iscsymf`, 、`__iswcsymf`, 、`_iscsym_l`, 、`_iswcsym_l`, 、`_iscsymf_l`, 、および `_iswcsymf_l` のルーチンは、Microsoft 固有の仕様です。 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 参照  
 [文字分類](../../c-runtime-library/character-classification.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)