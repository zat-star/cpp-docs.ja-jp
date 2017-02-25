---
title: "_get_osfhandle | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_osfhandle"
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
  - "get_osfhandle"
  - "_get_osfhandle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "オペレーティング システム、ファイル ハンドルの取得"
  - "get_osfhandle 関数"
  - "_get_osfhandle 関数"
  - "ファイル ハンドル [C++]、オペレーティング システム"
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _get_osfhandle
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定されたファイル記述子に関連付けられたオペレーティング システムのファイル ハンドルを取得します。  
  
## 構文  
  
```  
intptr_t _get_osfhandle(   
   int fd   
);  
```  
  
#### パラメーター  
 `fd`  
 一部のファイル記述子を返します。  
  
## 戻り値  
 `fd` が有効な場合、オペレーティング システムのファイル ハンドル。  それ以外の場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の継続が許可された場合、関数の戻り値 `INVALID_HANDLE_VALUE` \(–1\) に無効なファイルのハンドルを表示 `EBADF`とこの `errno` を設定します。  
  
## 解説  
 `_get_osfhandle`開くファイルを閉じるには `_close`を呼び出します。  基になるハンドルは、`_close`への呼び出しによって閉じるため、元のハンドルの Win32 関数 `CloseHandle` を呼び出す必要はありません。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_get_osfhandle`|\<io.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [\_close](../Topic/_close.md)   
 [\_creat、\_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_dup、\_dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [\_open、\_wopen](../../c-runtime-library/reference/open-wopen.md)