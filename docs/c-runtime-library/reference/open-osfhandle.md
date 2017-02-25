---
title: "_open_osfhandle | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_open_osfhandle"
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
  - "_open_osfhandle"
  - "open_osfhandle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "open_osfhandle 関数"
  - "ファイル ハンドル [C++]、関連付け"
  - "_open_osfhandle 関数"
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _open_osfhandle
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

既存のオペレーティング システムのファイル ハンドルと C\+\+.のランタイム ファイル記述子を関連付けます。  
  
## 構文  
  
```  
  
      int _open_osfhandle (  
   intptr_t osfhandle,  
   int flags   
);  
```  
  
#### パラメーター  
 `osfhandle`  
 オペレーティング システムのファイル ハンドル。  
  
 `flags`  
 許可される演算の型。  
  
## 戻り値  
 成功すると、`_open_osfhandle` .は C ランタイムのファイル記述子を返します。  それ以外の場合は–1 を返します。  
  
## 解説  
 `osfhandle`で指定された `_open_osfhandle` 関数は、.のランタイム ファイル記述子、それをオペレーティング システムのファイル ハンドルに、割り当てます。  `flags` の引数は Fcntl.h に定義されているマニフェスト定数の一つ以上から形成される整数式です。  `flags` 引数を形成するために複数の記号定数を使用する場合は、定数はビットごとの OR 演算子で結合されます。  **&#124;** \).  
  
 Fcntl.h は次のマニフェスト定数を定義します。  
  
 **\_O\_APPEND**  
 任意の書き込み操作の前にファイルの末尾にファイル ポインターを移動します。  
  
 **\_O\_RDONLY**  
 読み取り専用のファイルを開きます。  
  
 **\_O\_TEXT**  
 テキスト \(変換\) モードでファイルを開きます。  
  
 **\_O\_WTEXT**  
 Unicode \(翻訳 UTF\-16\) モードでファイルを開きます。  
  
 `_open_osfhandle`開くファイルを閉じるには `_close`を呼び出します。  基になるハンドルは、`_close`への呼び出しによって閉じるため、元のハンドルの Win32 関数 `CloseHandle` を呼び出す必要はありません。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_open_osfhandle`|\<io.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 同等の .NET Framework 関数  
 [System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)  
  
## 参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)