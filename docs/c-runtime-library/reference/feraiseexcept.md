---
title: "feraiseexcept | Microsoft Docs"
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
  - "feraiseexcept"
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
apitype: "HeaderDef"
f1_keywords: 
  - "feraiseexcept"
  - "fenv/feraiseexcept"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "feraiseexcept 関数"
ms.assetid: 87e89151-83c2-4563-9a9a-45666245d437
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# feraiseexcept
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定された浮動小数点例外を生成します。  
  
## 構文  
  
```  
int feraiseexcept(  
   int excepts  
);  
```  
  
#### パラメーター  
 `excepts`  
 発生させる浮動小数点の例外です。  
  
## 戻り値  
 指定された例外をすべてが正常に発生した場合は、0 を返します。  
  
## 解説  
 `feraiseexcept` 関数で指定された浮動小数点例外を生成しようとしました。 `excepts`します。`feraiseexcept` 関数は、\< fenv.h \> で定義されているこれらの例外マクロをサポートしています。  
  
|例外マクロ|説明|  
|-----------|--------|  
|可能性|前の手順浮動小数点演算では特異性またはポール エラーが発生しました無限大の値が作成されました。|  
|FE\_INEXACT|関数は、前の浮動小数点演算の格納された結果を丸める強制されました。|  
|ある|前の浮動小数点演算には、ドメイン エラーが発生しました。|  
|可能性|範囲エラーが発生しました。以前の浮動小数点演算の結果が長すぎて表示されます。|  
|される|以前の浮動小数点演算の結果が小さすぎるため、完全な精度; で表現denormal 値が作成されました。|  
|FE\_ALLEXCEPT|すべてのビットごとの OR は、浮動小数点例外をサポートします。|  
  
 `excepts` 引数が 0 の場合あります。 またはサポートされている例外マクロの 2 つ以上の例外マクロの値、またはビットごとの 1 つです。 可能性またはされるを指定した例外マクロのいずれかの場合は、副次効果と FE\_INEXACT 例外を発生する可能性があります。  
  
 この関数を使用するのには、浮動小数点の最適化を使用してアクセスを妨げる可能性のあるオフにする必要があります、 `#pragma fenv_access(on)` 呼び出しの前にディレクティブです。 詳細については、「[fenv\_access](../../preprocessor/fenv-access.md)」を参照してください。  
  
 **Microsoft 固有の仕様:** で指定された例外 `excepts` ある、という順序で発生する可能性、可能性、される、FE\_INEXACT です。 ただし、FE\_INEXACT 生成されることが可能性またはされるが発生したときに指定されていない場合でも `excepts`します。**END Microsoft 固有の仕様**  
  
## 必要条件  
  
|関数|C ヘッダー|C\+\+ ヘッダー|  
|--------|------------|----------------|  
|`feraiseexcept`|\<fenv.h\>|\<cfenv\>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetexceptflag](../Topic/fesetexceptflag2.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fetestexcept](../Topic/fetestexcept1.md)   
 [feupdateenv](../Topic/feupdateenv.md)