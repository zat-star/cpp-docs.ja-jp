---
title: "_ismbbalpha、_ismbbalpha_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbbalpha"
  - "_ismbbalpha_l"
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
  - "ismbbalpha"
  - "ismbbalpha_l"
  - "_ismbbalpha"
  - "_ismbbalpha_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ismbbalpha 関数"
  - "ismbbalpha_l 関数"
  - "_ismbbalpha 関数"
  - "_ismbbalpha_l 関数"
ms.assetid: 8e54cb92-fc2b-41f5-8ab4-b22ac8aa9ad0
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _ismbbalpha、_ismbbalpha_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定されたマルチバイト文字が英字かどうかを判定します。  
  
## 構文  
  
```  
int _ismbbalpha(  
   unsigned int c   
);  
int _ismbbalpha_l(  
   unsigned int c   
);  
```  
  
#### パラメーター  
 `c`  
 テストする整数。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 `_ismbbalpha` は、式が以下の場合に 0 以外の値を返します。  
  
```  
isalpha || _ismbbkalnum  
```  
  
 `c` の場合は 0 以外の値、それ以外の場合は 0 です。`_ismbbalpha` は、ロケールに依存する任意の文字設定に現在のロケールを使用します。`_ismbbalpha_l` は、代わりに渡されるロケールを使用することを除いて同じです。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_ismbbalpha`|\<mbctype.h\>|  
|`_ismbbalpha_l`|\<mbctype.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [バイト分類](../../c-runtime-library/byte-classification.md)   
 [\_ismbb 系ルーチン](../../c-runtime-library/ismbb-routines.md)