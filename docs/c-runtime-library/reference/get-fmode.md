---
title: "_get_fmode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_fmode"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_fmode"
  - "_get_fmode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_get_fmode 関数"
  - "ファイル変換 [C++], 既定のモード"
  - "get_fmode 関数"
ms.assetid: 22ea70e2-b9b5-422d-b514-64f4beaea45c
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _get_fmode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

既定のファイルをファイル I\/O 操作の変換モードを取得します。  
  
## 構文  
  
```  
errno_t _get_fmode(   
   int * pmode   
);  
```  
  
#### パラメーター  
 \[出力\] `pmode`  
 現在の既定のモードとして格納する整数へのポインター。: `_O_TEXT` または `_O_BINARY`。  
  
## 戻り値  
 正常終了した場合は;を返します 失敗した場合はエラー コード。  `pmode` が `NULL`の場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)で呼び出されます。  実行の継続が許可された場合、`errno` が `EINVAL` に設定され、関数から `EINVAL` が返されます。  
  
## 解説  
 関数は [\_fmode](../../c-runtime-library/fmode.md) のグローバル変数の値を取得します。  この変数は、低レベルの両方の変換モードは既定のファイルを指定し、`_open`、`_pipe`、`fopen`と `freopen`などのファイル I\/O 操作を、ストリーミング\)。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|----------|------------|----------------|  
|`_get_fmode`|\<stdlib.h\>|\<fcntl.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 [\_set\_fmode](../../c-runtime-library/reference/set-fmode.md)の例を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [\_fmode](../../c-runtime-library/fmode.md)   
 [\_set\_fmode](../../c-runtime-library/reference/set-fmode.md)   
 [\_setmode](../../c-runtime-library/reference/setmode.md)   
 [テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)