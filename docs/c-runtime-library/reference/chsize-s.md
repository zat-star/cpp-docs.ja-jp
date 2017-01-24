---
title: "_chsize_s | Microsoft Docs"
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
  - "_chsize_s"
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
  - "chsize_s"
  - "_chsize_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_chsize_s 関数"
  - "chsize_s 関数"
  - "ファイル [C++], 変更 (サイズを)"
ms.assetid: d88d2e94-6e3b-42a5-8631-16ac4d82fa38
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _chsize_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルのサイズを変更します。  これは [CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)"に説明されているように、セキュリティが強化された [\_chsize](../../c-runtime-library/reference/chsize.md) のバージョンです。  
  
## 構文  
  
```  
errno_t _chsize_s(   
   int fd,  
   __int64 size   
);  
```  
  
#### パラメーター  
 `fd`  
 開いているファイルを参照するファイル記述子。  
  
 `size`  
 バイトのファイルの新しい長さ。  
  
## 戻り値  
 `_chsize_s`はファイル サイズが正常に変更された場合は値 0 を返します。  0 以外のな戻り値はエラーを示します: 戻り値は、サイズが小さい場合領域がデバイスに残っている場合、または `EINVAL`に指定されたファイルが読み取り専用であるか、記述子が無効な場合、指定したファイルがアクセスに対してロックされて `EACCES`、`EBADF`、`ENOSPC`。  `errno`は同じ値に設定されます。  
  
 リターン コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `_chsize_s`関数は `size`で指定された長さに `fd` に関連付けられたファイルを拡張するか、切り捨てられます。  ファイルはモードで開く必要ための書き込み。  ファイルがまで null 文字 \(「\\0」\) が付けられます。  ファイルが切り詰められている場合、簡略化されたファイルの末尾からファイルの元の長さへのすべてのデータは失われます。  
  
 したがって`_chsize_s`はファイル サイズとして 64 ビットの整数を受け取り、ファイル サイズを超える 4 GB を処理できます。  `_chsize`は 32 ビット ファイル サイズに制限されます。  
  
 この関数は、パラメーターを検証します。  `fd` に有効なファイル記述子がない場合、またはサイズが小さい場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|----------|------------|----------------|  
|`_chsize_s`|\<io.h\>|\<errno.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
  
-   [System::IO::Stream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.stream.setlength.aspx)  
  
-   [System::IO::FileStream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.filestream.setlength.aspx)  
  
## 参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [\_chsize](../../c-runtime-library/reference/chsize.md)   
 [\_close](../Topic/_close.md)   
 [\_creat、\_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open、\_wopen](../../c-runtime-library/reference/open-wopen.md)