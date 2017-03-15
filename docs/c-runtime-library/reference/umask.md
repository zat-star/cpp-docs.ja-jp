---
title: "_umask | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_umask"
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
  - "_umask"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_umask 関数"
  - "ファイルのアクセス許可 [C++]"
  - "ファイル [C++], アクセス許可の設定"
  - "マスク"
  - "マスク, ファイルのアクセス許可の設定"
  - "umask 関数"
ms.assetid: 5e9a13ba-5321-4536-8721-6afb6f4c8483
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _umask
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

既定のファイルのアクセス許可マスクを設定します。  この関数のセキュリティが強化されたバージョンについては、「[\_umask\_s](../Topic/_umask_s.md)」を参照してください。  
  
## 構文  
  
```  
int _umask(  
   int pmode   
);  
```  
  
#### パラメーター  
 `pmode`  
 既定のアクセス許可の設定。  
  
## 戻り値  
 `_umask` は `pmode`の以前の値を返します。  エラーの戻り値はありません。  
  
## 解説  
 モードへの現在のプロセスのファイル アクセス許可が `pmode`マスクで指定した `_umask` 関数のセット*。*ファイルのアクセス許可マスクは `_creat`、`_open`、または `_sopen`によって作成された新しいファイルのアクセス許可設定を変更します。  マスクに 1 は 0 に、ファイルが要求するアクセス許可値の対応するビットが設定されています \(拒否\) です。  マスクには、対応する 0 ビット、不変少なくなります。  新しいファイルのアクセス許可は、ファイルが初めて閉じるまで設定されません。  
  
 整数式 `pmode` は SYS\\STAT.H で次の記号定数 1 のいずれかまたは両方を定義して含まれています:  
  
 `_S_IWRITE`  
 許可される書き込み。  
  
 `_S_IREAD`  
 許可される読み取り。  
  
 `_S_IREAD | _S_IWRITE`  
 許可されるの読み取りと書き込み。  
  
 定数は、両方とも提供されると、ビットごとの OR 演算子で結合されます。          `|`  \).  `pmode` の引数が `_S_IREAD`は、読み取ることはできません \(ファイルは書き込み専用です\)。  `pmode` の引数が `_S_IWRITE`の場合、書き込むことはできません \(ファイルは読み取り専用です。  たとえば、書き込みビットがマスクに設定されている場合、新しいファイルが読み取り専用です。  MS\-DOS および Windows オペレーティング システムと、すべてのファイルを読み取ることができることに注意してください; 書き込み専用アクセス許可を与えることはできません。  したがって、`_umask` の読み取り専用ビットを設定すると、ファイルのモードには影響しません。  
  
 `pmode` がマニフェスト定数の 1 種類の組み合わせで、別の一連の定数を組み込む、それらは無視されます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_umask`|\<io.h、sys\> \<\/stat.h、sys\/\>types.h \<\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 使用例  
  
```  
// crt_umask.c  
// compile with: /W3  
// This program uses _umask to set  
// the file-permission mask so that all future  
// files will be created as read-only files.  
// It also displays the old mask.  
#include <sys/stat.h>  
#include <sys/types.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int oldmask;  
  
   /* Create read-only files: */  
   oldmask = _umask( _S_IWRITE ); // C4996  
   // Note: _umask is deprecated; consider using _umask_s instead  
   printf( "Oldmask = 0x%.4x\n", oldmask );  
}  
```  
  
  **Oldmask \= 0x0000**   
## 同等の .NET Framework 関数  
 [System::IO::File::SetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.setattributes.aspx)  
  
## 参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [下位入出力](../../c-runtime-library/low-level-i-o.md)   
 [\_chmod、\_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_creat、\_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_mkdir、\_wmkdir](../Topic/_mkdir,%20_wmkdir.md)   
 [\_open、\_wopen](../../c-runtime-library/reference/open-wopen.md)