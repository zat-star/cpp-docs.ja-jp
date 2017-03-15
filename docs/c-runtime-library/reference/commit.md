---
title: "_commit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_commit"
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
  - "_commit"
  - "commit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_commit 関数"
  - "commit 関数"
  - "コミット (ファイルをディスクに)"
  - "ファイル [C++], フラッシュ"
  - "フラッシュ (ファイルからディスクに)"
ms.assetid: d0c74d3a-4f2d-4fb0-b140-2d687db3d233
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _commit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルをディスクに直接フラッシュします。  
  
## 構文  
  
```  
int _commit(   
   int fd   
);  
```  
  
#### パラメーター  
 `fd`  
 開いているファイルを参照するファイル記述子。  
  
## 戻り値  
 `_commit` ファイルがディスクにフラッシュした場合は 0 を返します。  –1 の戻り値はエラーを示します。  
  
## 解説  
 `_commit` 関数は、オペレーティング システムに `fd` に関連付けられたファイルをディスクに変更する。  この呼び出しは、指定したファイルが、フラッシュされていることを確認して、オペレーティング システムの細心です。  
  
 `fd` が無効なファイル記述子の場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の継続 `EBADF`への関数の戻り値は \-1 と `errno` 設定されます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|省略可能なヘッダー|  
|----------|------------|---------------|  
|`_commit`|\<io.h\>|\<errno.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 参照  
 [下位入出力](../../c-runtime-library/low-level-i-o.md)   
 [\_creat、\_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open、\_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_read](../Topic/_read.md)   
 [\_write](../../c-runtime-library/reference/write.md)