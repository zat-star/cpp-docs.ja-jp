---
title: "isnan、_isnan、_isnanf | Microsoft Docs"
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
  - "_isnan"
  - "_isnanf"
  - "isnan"
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
  - "_isnan"
  - "isnan"
  - "math/isnan"
  - "math/_isnan"
  - "math/_isnanf"
  - "_isnanf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "NaN (非数)"
  - "_isnan 関数"
  - "IEEE 浮動小数点表現"
  - "非数 (NaN)"
  - "isnan 関数"
ms.assetid: 391fbc5b-89a4-4fba-997e-68f1131caf82
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# isnan、_isnan、_isnanf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

浮動小数点値が数値 \(NAN\) ではないかどうか。  
  
## 構文  
  
```  
int isnan(  
   /* floating-point */ x   
); /* C-only macro */  
  
int _isnan(  
   double x   
);  
  
int _isnanf(  
   float x  
); /* x64 only */  
  
template <class T>  
bool isnan(  
   T x  
) throw(); /* C++ only */  
```  
  
#### パラメーター  
 *x*  
 テストする浮動小数点値。  
  
## 戻り値  
 C では、 `isnan` マクロと `_isnan` と `_isnanf` 場合、関数は 0 以外の値を返す引数 `x` NAN; は、それ以外の場合 0 を返します。  
  
 C\+\+ では、 `isnan` 関数を返します。 テンプレート `true` 場合引数 `x` NAN; は、返されるそれ以外の場合 `false`します。  
  
## 解説  
 C `isnan` マクロと `_isnan` と `_isnanf` 関数は浮動小数点値をテスト *x*, 、0 以外の値を返す場合 *x* ない数 \(NAN\) 値です。 浮動小数点演算の結果は、指定した型の IEEE 754 浮動小数点形式で表現できない場合は、NAN が生成されます。 出力は NAN を表現する方法については、次を参照してください。 [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)します。  
  
 C\+\+ としてコンパイルするとき、 `isnan` マクロが定義されていないと `isnan` テンプレート関数が代わりに定義されています。 型の値を返す `bool` 整数ではなく。  
  
 `_isnan` と `_isnanf` 関数は、Microsoft 固有の仕様です。`_isnanf` 関数は、x64 用にコンパイルされるときに使用できるのみです。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー \(C\)|必須ヘッダー \(C\+\+\)|  
|----------|------------------|----------------------|  
|`isnan`, `_isnanf`|\<math.h\>|\<math.h\> または \<cmath\>|  
|`_isnan`|\<float.h\>|\< float.h \> または \< cfloat \>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [\_finite、\_finitef](../../c-runtime-library/reference/finite-finitef.md)   
 [\_fpclass \_fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)