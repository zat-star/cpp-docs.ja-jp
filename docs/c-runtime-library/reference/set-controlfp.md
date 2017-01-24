---
title: "_set_controlfp | Microsoft Docs"
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
  - "_set_controlfp"
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
  - "set_controlfp"
  - "_set_controlfp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_set_controlfp 関数"
  - "浮動小数点関数, 設定 (制御ワードを)"
  - "set_controlfp 関数"
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _set_controlfp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

浮動小数点制御ワードを設定します。  
  
## 構文  
  
```  
void __cdecl _set_controlfp(  
    unsigned int newControl,  
    unsigned int mask  
);  
```  
  
#### パラメーター  
 `newControl`  
 新しい制御ワードのビット値。  
  
 `mask`  
 新しく設定する制御ワード ビットのマスク。  
  
## 戻り値  
 なし。  
  
## 解説  
 `_set_controlfp` は `_control87`に似ていますが、`newControl`のみ浮動小数点制御ワードを設定します。  この値のビットは、浮動小数点のコントロールの状態を示します。  浮動小数点のコントロールの状態を使用すると、プログラムで使用する浮動小数点演算パッケージの精度、丸め、および無限大の各モードを変更できます。  `_set_controlfp` を使用して、浮動小数点例外のマスクの設定および解除を行うこともできます。  詳細については、「[\_control87、\_controlfp、\_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md)」を参照してください。  
  
 共通言語ランタイムは浮動小数点の既定の精度のみをサポートするため、[\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md) または `/clr:pure` を使用してコンパイルする場合、この関数は使用しないでください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|互換性|  
|----------|------------|---------|  
|`_set_controlfp`|\<float.h\>|x86 プロセッサのみ|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [\_clear87、\_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [\_status87、\_statusfp、\_statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)