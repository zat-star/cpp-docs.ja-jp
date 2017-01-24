---
title: "_creat、_wcreat | Microsoft Docs"
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
  - "_creat"
  - "_wcreat"
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
  - "wcreat"
  - "_wcreat"
  - "_creat"
  - "tcreat"
  - "_tcreat"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "wcreat 関数"
  - "_wcreat 関数"
  - "ファイル [C++]、作成"
  - "_creat 関数"
  - "tcreat 関数"
  - "creat 関数"
  - "_tcreat 関数"
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _creat、_wcreat
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

新しいファイルを作成します。  `_creat` と `_wcreat` は推奨されて; [\_sopen\_s、\_wsopen\_s](../../c-runtime-library/reference/sopen-s-wsopen-s.md) を代わりに使用します。  
  
## 構文  
  
```  
int _creat(   
   const char *filename,  
   int pmode   
);  
int _wcreat(   
   const wchar_t *filename,  
   int pmode   
);  
```  
  
#### パラメーター  
 `filename`  
 新しいファイルの名前。  
  
 `pmode`  
 アクセス許可の設定。  
  
## 戻り値  
 これらの関数は、作成されるファイルは、成功すると、ファイル記述子を返します。  そうしないと、関数は次の表に示すように–1 と設定 `errno` を返します。  
  
|`errno` の設定|説明|  
|-----------------|--------|  
|`EACCES`|`filename` は 既存の読み取り専用ファイルを指定するか、ファイルの代わりに指定します。|  
|`EMFILE`|これ以上のファイル記述子は使用できません。|  
|`ENOENT`|指定されたファイルが見つかりません。|  
  
 `filename` が null の場合、これらの関数は [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、\-1 を返します。  
  
 リターン コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `_creat` 関数では新しいファイルを作成するか、または既存の 1 を開き、切り捨てられます。  `_wcreat` 関数は、`_creat` 関数のワイド文字バージョンです。`_wcreat` 関数の引数 `filename` は、ワイド文字列です。  それ以外では、`_wcreat` と `_creat` の動作は同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tcreat`|`_creat`|`_creat`|`_wcreat`|  
  
 `filename` で指定されたファイルが見つからない場合、新しいファイルが特定のアクセス許可の設定で作成され、書き込み用に開きます。  ファイルが既にと書き込みアクセス許可の設定を使用する場合 `_creat` は長さ 0 にファイルを開き、前の内容を切り捨てておよび書き込み用の破棄します。  アクセス許可の設定、`pmode`、新しく作成されたファイルだけに適用されます。  新しいファイルを最初に終了した後に指定されたアクセス許可設定を受け取ります。  整数式 `pmode` は SYS\\Stat.h でマニフェスト定数 `_S_IWRITE` と `_S_IREAD`1 のいずれかまたは両方を定義しています。  定数は、両方とも提供されると、`OR` のビットごとのな演算子と結合されます。  **&#124;**\).  `pmode` パラメーターには、次の値の 1 に設定されます。  
  
|値|定義|  
|-------|--------|  
|`_S_IWRITE`|許可される書き込み。|  
|`_S_IREAD`|許可される読み取り。|  
|`_S_IREAD &#124; _S_IWRITE`|許可されるの読み取りと書き込み。|  
  
 記述するアクセス許可、ファイルが読み取り専用されません。  すべてのファイルを読み取り、常に;です 書き込み専用アクセス許可を与えることは不可能です。  `_S_IWRITE` モードと `_S_IREAD``| _S_IWRITE` は、等価です。  `_creat` で開くファイルは `_SH_DENYNO`の互換モード \([\_sopen](../../c-runtime-library/reference/sopen-wsopen.md)を参照してください\) 常に表示されます。  
  
 `_creat` は `pmode` にアクセス許可を設定する前に、ファイルのアクセス許可マスクを適用します \([\_umask](../../c-runtime-library/reference/umask.md)を参照してください。  `_creat` は 前のライブラリとの互換性が主に与えられます。  `_O_CREAT` の `_open` と `oflag` パラメーターの `_O_TRUNC` の呼び出しは `_creat` に相当し、新しいコードの使用をお勧めします。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|----------|------------|----------------|  
|`_creat`|\<io.h\>|\<sys\/types.h、sys\> \<\/stat.h、errno.h\> \<\>|  
|`_wcreat`|\<io.h または\> wchar.h \<\>|\<sys\/types.h、sys\> \<\/stat.h、errno.h\> \<\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_creat.c  
// compile with: /W3  
// This program uses _creat to create  
// the file (or truncate the existing file)  
// named data and open it for writing.  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int fh;  
  
   fh = _creat( "data", _S_IREAD | _S_IWRITE ); // C4996  
   // Note: _creat is deprecated; use _sopen_s instead  
   if( fh == -1 )  
      perror( "Couldn't create data file" );  
   else  
   {  
      printf( "Created data file.\n" );  
      _close( fh );  
   }  
}  
```  
  
  **作成されたデータ ファイル。**   
## 参照  
 [下位入出力](../../c-runtime-library/low-level-i-o.md)   
 [\_chmod、\_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_chsize](../../c-runtime-library/reference/chsize.md)   
 [\_close](../Topic/_close.md)   
 [\_dup、\_dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [\_open、\_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_sopen、\_wsopen](../../c-runtime-library/reference/sopen-wsopen.md)   
 [\_umask](../../c-runtime-library/reference/umask.md)