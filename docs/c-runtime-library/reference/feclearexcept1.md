---
title: "feclearexcept1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "feclearexcept"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "feclearexcept"
  - "fenv/feclearexcept"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "feclearexcept 関数"
ms.assetid: ef419da3-c248-4432-b53c-8e7a475d9533
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# feclearexcept
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

引数に指定された浮動小数点例外フラグをクリアしようとします。  
  
## 構文  
  
```  
int feclearexcept(  
   int excepts  
);  
```  
  
#### パラメーター  
 `excepts`  
 例外状態フラグをオフにします。  
  
## 戻り値  
 場合は 0 を返します `excepts` ゼロ、または指定された例外をすべてが正常にクリアされた場合。 それ以外の場合、0 以外の値を返します。  
  
## 解説  
 `feclearexcept` 浮動をオフにしようと関数ポイントで指定された例外状態フラグ `excepts`します。 この関数には、fenv.h で定義されているこれらの例外マクロがサポートされています。  
  
|例外マクロ|説明|  
|-----------|--------|  
|可能性|前の手順浮動小数点演算では特異性またはポール エラーが発生しました無限大の値が作成されました。|  
|FE\_INEXACT|この関数は、前の浮動小数点演算の格納された結果を丸める強制されました。|  
|ある|前の浮動小数点演算には、ドメイン エラーが発生しました。|  
|可能性|範囲エラーが発生しました。以前の浮動小数点演算の結果が長すぎて表示されます。|  
|される|以前の浮動小数点演算の結果が小さすぎるため、完全な精度; で表現denormal 値が作成されました。|  
|FE\_ALLEXCEPT|すべてのビットごとの OR は、浮動小数点例外をサポートします。|  
  
 `excepts` ゼロ、またはサポートされている例外マクロの 1 つ以上のビットごとの OR を引数として使用することがあります。 その他の引数値の結果は未定義です。  
  
## 必要条件  
  
|関数|C ヘッダー|C\+\+ ヘッダー|  
|--------|------------|----------------|  
|`feclearexcept`|\<fenv.h\>|\<cfenv\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fetestexcept](../Topic/fetestexcept1.md)