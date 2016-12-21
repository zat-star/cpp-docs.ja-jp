---
title: "nextafter、nextafterf、nextafterl、_nextafter、_nextafterf、nexttoward、nexttowardf、nexttowardl | Microsoft Docs"
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
  - "nextafterf"
  - "_nextafterf"
  - "nextafter"
  - "nextafterl"
  - "_nextafter"
  - "nexttoward"
  - "nexttowardf"
  - "nexttowardl"
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
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "nextafter"
  - "_nextafter"
  - "nextafterf"
  - "nextafterl"
  - "_nextafterf"
  - "math/nextafter"
  - "math/nextafterf"
  - "math/nextafterl"
  - "nexttoward"
  - "nexttowardf"
  - "nexttowardl"
  - "math/nexttoward"
  - "math/nexttowardf"
  - "math/nexttowardl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_nextafter 関数"
  - "nextafter 関数"
  - "_nextafterf 関数"
  - "nextafterf 関数"
  - "nextafterl 関数"
  - "nexttoward 関数"
  - "nexttowardf 関数"
  - "nexttowardl 関数"
ms.assetid: 9785bfb9-de53-4bd0-9637-f05fa0c1f6ab
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# nextafter、nextafterf、nextafterl、_nextafter、_nextafterf、nexttoward、nexttowardf、nexttowardl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

次の表現可能な浮動小数点値を返します。  
  
## 構文  
  
```  
double nextafter(  
   double x,  
   double y   
);  
  
float nextafter(  
   float x,  
   float y   
); /* C++ only, requires <cmath> */  
  
long double nextafter(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nextafterf(  
   float x,  
   float y   
);   
  
long double nextafterl(  
   long double x,  
   long double y   
);  
  
double _nextafter(  
   double x,  
   double y   
);  
  
float _nextafterf(  
   float x,  
   float y   
); /* x64 only */  
  
double nexttoward(  
   double x,  
   long double y   
);  
  
float nexttoward(  
   float x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
long double nexttoward(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nexttowardf(  
   float x,  
   long double y   
);   
  
long double nexttowardl(  
   long double x,  
   long double y   
);  
```  
  
#### パラメーター  
 `x`  
 起動する浮動小数点値。  
  
 `y`  
 方向に移動する浮動小数点値。  
  
## 戻り値  
 戻り値の型の後の次の表現可能な浮動小数点値を返す `x` の方向に `y`します。 場合 `x`\=`y`, 、返します `y`, ない例外がトリガーされると、戻り値の型に変換されます。 場合 `x` と等しくない `y`, と、結果は、denormal でも 0 でも、されると FE\_INEXACT の浮動小数点例外状態を設定すると、および正しい結果が返されます。 いずれか `x` または `y` が NAN の場合、戻り値は、入力の Nan のいずれかです。 場合 `x` 有限し、結果は無限、または型で表現できません、正しく署名された infinity または NAN が返される、可能性と FE\_INEXACT 浮動小数点例外の状態が設定されていると `errno` ERANGE に設定されています。  
  
## 解説  
 `nextafter` と `nexttoward` 関数ファミリは同等のパラメーターの型を除く、 `y`です。 場合 `x` と `y` が戻り値が等しい、 `y` 戻り値の型に変換します。  
  
 C\+\+ が \< cmath \> を指定する場合、オーバー ロードを使用するためのオーバー ロードを呼び出すことができます `nextafter` と `nexttoward` 値を返す `float` と `long double` 型です。 C プログラムでは `nextafter` と `nexttoward` いつでも `double`します。  
  
 `_nextafter` と `_nextafterf` の関数は、Microsoft 固有の仕様です。`_nextafterf` 関数は、x64 コンパイルするときにのみ使用できます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー \(C\)|必須ヘッダー \(C\+\+\)|  
|----------|------------------|----------------------|  
|`nextafter`, `nextafterf`, `nextafterl`, `_nextafterf`, `nexttoward`, `nexttowardf`, `nexttowardl`|\<math.h\>|\<math.h\> または \<cmath\>|  
|`_nextafter`|\<float.h\>|\< float.h \> または \< cfloat \>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [isnan、\_isnan、\_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)