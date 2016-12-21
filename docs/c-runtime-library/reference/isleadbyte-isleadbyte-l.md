---
title: "isleadbyte、_isleadbyte_l | Microsoft Docs"
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
  - "_isleadbyte_l"
  - "isleadbyte"
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
  - "_istleadbyte"
  - "_isleadbyte_l"
  - "isleadbyte"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "先行バイト"
  - "_isleadbyte_l 関数"
  - "_istleadbyte 関数"
  - "istleadbyte 関数"
  - "isleadbyte 関数"
ms.assetid: 3b2bcf09-d82b-4803-9e80-59d04942802a
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# isleadbyte、_isleadbyte_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字がマルチバイト文字の先行バイトかどうかを判定します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
int isleadbyte(  
   int c   
);  
int _isleadbyte_l(  
   int c   
);  
```  
  
#### パラメーター  
 `c`  
 テストする整数。  
  
## 戻り値  
 `isleadbyte` では、引数がテスト条件を満たす場合に 0 以外の値が返され、テスト条件を満たさない場合に 0 が返されます。 "C" ロケールと 1 バイト文字セット \(SBCS\) のロケールでは、`isleadbyte` は常に 0 を返します。  
  
## 解説  
 `isleadbyte` のマクロは、引数がマルチバイト文字の先行バイトの場合に 0 以外の値を返します。`isleadbyte` は –1 \(`EOF`\) から `UCHAR_MAX` \(0xFF\) までの任意の整数の引数に対して意味のある結果を生成します。  
  
 `isleadbyte` の予想される引数の型は `int` です。符号付き文字が渡されると、コンパイラはこれを符号拡張して整数に変換し、予期しない結果が生じる場合があります。  
  
 この関数の `_l` サフィックスが付いたバージョンは、サフィックスが付いていないバージョンと同じですが、ロケールに依存する動作については、現在のロケールではなく渡されたロケールを使用する点が異なります。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_istleadbyte`|常に false を返します|**\_** `isleadbyte`|常に false を返します|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`isleadbyte`|\<ctype.h\>|  
|`_isleadbyte_l`|\<ctype.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 該当するものはありません。ただし、「[System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)」を参照してください。  
  
## 参照  
 [バイト分類](../../c-runtime-library/byte-classification.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [\_ismbb 系ルーチン](../../c-runtime-library/ismbb-routines.md)