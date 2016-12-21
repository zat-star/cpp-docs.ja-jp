---
title: "_setmaxstdio | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_setmaxstdio"
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
  - "setmaxstdio"
  - "_setmaxstdio"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_setmaxstdio 関数"
  - "開いているファイルの最大数"
  - "開く (ファイルを), 最大"
  - "setmaxstdio 関数"
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _setmaxstdio
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`stdio` レベルで開いているファイルの数の最大値を同時に設定します。  
  
## 構文  
  
```  
int _setmaxstdio(  
   int newmax   
);  
```  
  
#### パラメーター  
 `newmax`  
 同時に `stdio` レベルで開いているファイルの数の新しい最大値。  
  
## 戻り値  
 正常終了した場合 `newmax` ;を返します 別の方法で–1。  
  
 `newmax` が `_IOB_ENTRIES` 未満以上の場合、オペレーティング システムで使用できるハンドルの最大数無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の継続が許可された場合、この関数は \-1 を返し、`errno` を `EINVAL` に設定します。  
  
 エラー コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `_setmaxstdio` の関数の変更 `stdio` レベルで同時に開くことができるファイル数の最大値。  
  
 C ランタイム I\/O は、以前のバージョンの Win32 プラットフォームの多くのファイルをサポートします。  2,048 個のファイルは [lowio のレベル](../../c-runtime-library/low-level-i-o.md) で同時に表示されます \(つまり、I\/O の関数の `_open`、`_read`、`_write`などのファミリによって"、"アクセスされます\)。  512 個のファイルは [stdio のレベル](../../c-runtime-library/stream-i-o.md) で同時に表示されます \(つまり、関数の `fopen`、`fgetc`、`fputc`などのファミリによって"、"アクセスされます\)。  `stdio` レベルの 512 のファイルの制限は `_setmaxstdio` 関数によって最大 2,048 にすることができます。  
  
 `stdio`レベルの関数が、`fopen`などの `lowio` 関数の上部にあるビルドされ、最大 2,048 は C ランタイム ライブラリを通じてアクセスする開いているファイルの数に対して同時に強力な上限値です。  
  
> [!NOTE]
>  この上限値は、サポートされる機能を超えて特定 Win32 プラットフォームと構成によって場合があります。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_setmaxstdio`|\<stdio.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 `_setmaxstdio`使用例については、" [\_getmaxstdio](../../c-runtime-library/reference/getmaxstdio.md) を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)