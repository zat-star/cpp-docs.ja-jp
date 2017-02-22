---
title: "_rmdir、_wrmdir | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wrmdir"
  - "_rmdir"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "trmdir"
  - "_trmdir"
  - "wrmdir"
  - "_rmdir"
  - "_wrmdir"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_rmdir 関数"
  - "_trmdir 関数"
  - "_wrmdir 関数"
  - "ディレクトリ [C++], 削除"
  - "ディレクトリ [C++], 削除"
  - "rmdir 関数"
  - "trmdir 関数"
  - "wrmdir 関数"
ms.assetid: 652c2a5a-b0ac-4493-864e-1edf484333c5
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _rmdir、_wrmdir
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ディレクトリを削除します。  
  
## 構文  
  
```  
  
      int _rmdir(  
   const char *dirname   
);  
int _wrmdir(  
   const wchar_t *dirname   
);  
```  
  
#### パラメーター  
 `dirname`  
 削除するディレクトリのパス。  
  
## 戻り値  
 これらの関数は、ディレクトリが正常に削除された場合は 0 を返します。  –1 の戻り値はエラーと `errno` を次の値の 1 に設定されていることを示す:  
  
 **ENOTEMPTY**  
 指定されたパスがディレクトリではありませんが、ディレクトリが空でない場合、またはディレクトリは現在のディレクトリ、またはルート ディレクトリです。  
  
 `ENOENT`  
 パスが無効です。  
  
 **EACCES**  
 プログラムのディレクトリに開かれたハンドルがあります。  
  
 リターン コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `_rmdir` 関数は `dirname`で指定されたディレクトリを削除します。  ディレクトリが空でない場合は、現在のディレクトリ、またはルート ディレクトリである必要があります。  
  
 `_wrmdir` 関数は、`_rmdir` 関数のワイド文字バージョンです。`_wrmdir` 関数の引数 `dirname` は、ワイド文字列です。  それ以外では、`_wrmdir` と `_rmdir` の動作は同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_trmdir`|`_rmdir`|`_rmdir`|`_wrmdir`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_rmdir`|\<direct.h\>|  
|`_wrmdir`|\<direct.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 使用例  
 [\_mkdir](../Topic/_mkdir,%20_wmkdir.md)"の例を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::IO::Directory::Delete](https://msdn.microsoft.com/en-us/library/system.io.directory.delete.aspx)  
  
## 参照  
 [ディレクトリ制御](../../c-runtime-library/directory-control.md)   
 [\_chdir、\_wchdir](../Topic/_chdir,%20_wchdir.md)   
 [\_mkdir、\_wmkdir](../Topic/_mkdir,%20_wmkdir.md)