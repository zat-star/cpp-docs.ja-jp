---
title: "rename、_wrename | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "rename"
  - "_wrename"
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
  - "_wrename"
  - "_trename"
  - "Rename"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_trename 関数"
  - "_wrename 関数"
  - "ディレクトリ [C++], 名前を変更"
  - "ファイル [C++], 名前を変更"
  - "名前 [C++], 変更 (ディレクトリを)"
  - "名前 [C++], 変更 (ファイルを)"
  - "rename 関数"
  - "名前を変更 (ディレクトリの)"
  - "名前を変更 (ファイルの)"
  - "trename 関数"
  - "wrename 関数"
ms.assetid: 9f0a6103-26a2-4dda-b14b-79a48946266a
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# rename、_wrename
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルまたはディレクトリの名前を変更します。  
  
## 構文  
  
```  
  
      int rename(  
   const char *oldname,  
   const char *newname   
);  
int _wrename(  
   const wchar_t *oldname,  
   const wchar_t *newname   
);  
```  
  
#### パラメーター  
 *oldname*  
 古い名前へのポインター。  
  
 *newname*  
 新しい名前へのポインター。  
  
## 戻り値  
 これらの関数は、正常終了した場合は 0 を返します。  エラー、関数の戻り値 0 以外の値と次の値のいずれか 1 つがに設定 `errno` :  
  
 `EACCES`  
 *newname* で指定されたファイルまたはディレクトリが存在するか、作成できません \(無効なパス\) ; または *oldname は* ディレクトリで、*newname は* 別のパスを指定します。  
  
 `ENOENT`  
 が *oldname* でファイルまたは指定したパス。  
  
 `EINVAL`  
 名前に無効な文字が含まれています。  
  
 そのほかの有効な戻り値については、[\_doserrno、\_errno、syserrlist および\_sys\_nerr "](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)を参照してください。  
  
## 解説  
 **名前の変更** 関数は *newname*で指定された名前に *oldname* で指定されたファイルまたはディレクトリの名前を変更します。  古い名前は既存のファイルまたはディレクトリのパスを指定する必要があります。  新しい名前が既存のファイルまたはディレクトリの名前である必要があります。  1 個のディレクトリからファイルを別の場所に *newname* 引数の別のパスを指定してデバイスを移動するには、**名前の変更** を使用できます。  ただし、ディレクトリを移動するには、**名前の変更** を使用できません。  ディレクトリの名前を変更したり、コントロールを移動することはできません。  
  
 `_wrename` は **\_rename**のワイド文字バージョンであり、; `_wrename` への引数はワイド文字列です。  `_wrename` と **\_rename** は別の方法で同様に動作します。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_trename`|**名前の変更**|**名前の変更**|`_wrename`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|**名前の変更**|\<io.h または\> stdio.h \<\>|  
|`_wrename`|\<stdio.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 使用例  
  
```  
// crt_renamer.c  
/* This program attempts to rename a file named  
 * CRT_RENAMER.OBJ to CRT_RENAMER.JBO. For this operation  
 * to succeed, a file named CRT_RENAMER.OBJ must exist and  
 * a file named CRT_RENAMER.JBO must not exist.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   int  result;  
   char old[] = "CRT_RENAMER.OBJ", new[] = "CRT_RENAMER.JBO";  
  
   /* Attempt to rename file: */  
   result = rename( old, new );  
   if( result != 0 )  
      printf( "Could not rename '%s'\n", old );  
   else  
      printf( "File '%s' renamed to '%s'\n", old, new );  
}  
```  
  
## 出力  
  
```  
File 'CRT_RENAMER.OBJ' renamed to 'CRT_RENAMER.JBO'  
```  
  
## 同等の .NET Framework 関数  
 [System::IO::File::Move](https://msdn.microsoft.com/en-us/library/system.io.file.move.aspx)  
  
## 参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)