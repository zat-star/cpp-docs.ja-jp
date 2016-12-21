---
title: "_ungetch、_ungetwch、_ungetch_nolock、_ungetwch_nolock | Microsoft Docs"
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
  - "_ungetch_nolock"
  - "_ungetwch_nolock"
  - "_ungetwch"
  - "_ungetch"
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
  - "api-ms-win-crt-conio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_ungetch_nolock"
  - "ungetwch"
  - "ungetch_nolock"
  - "_ungetwch"
  - "ungetch"
  - "ungetwch_nolock"
  - "_ungetch"
  - "_ungettch_nolock"
  - "_ungettch"
  - "_ungetwch_nolock"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ungetch 関数"
  - "_ungetch_nolock 関数"
  - "_ungettch 関数"
  - "_ungettch_nolock 関数"
  - "_ungetwch 関数"
  - "_ungetwch_nolock 関数"
  - "文字, 戻す (コンソールに)"
  - "ungetch_nolock 関数"
  - "ungettch 関数"
  - "ungettch_nolock 関数"
  - "ungetwch 関数"
  - "ungetwch_nolock 関数"
ms.assetid: 70ae71c6-228c-4883-a57d-de6d5f873825
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ungetch、_ungetwch、_ungetch_nolock、_ungetwch_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンソールから読み取った最後の文字をプッシュします。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
int _ungetch(  
   int c   
);  
wint_t _ungetwch(  
   wint_t c   
);  
int _ungetch_nolock(  
   int c   
);  
wint_t _ungetwch_nolock(  
   wint_t c   
);  
```  
  
#### パラメーター  
 `c`  
 プッシュする文字。  
  
## 戻り値  
 成功した場合は、どちらの関数も文字 `c` を返します。  エラーが発生した場合は、`_ungetch` は `EOF` と `_ungetwch`の戻り`WEOF`の値を返します。  
  
## 解説  
 これらの関数は `_getch` で次に読み取られた文字または `_getche` 押します \(または`_getwch` または`_getwche`\) 実行するに `c` が発生すると、コンソールに文字を `c`。  次が読み取られる前に複数回呼び出されると、`_ungetch` および `_ungetwch` は失敗します。  `c` 引数は `EOF` \(または `WEOF`\) にはならない場合があります。  
  
 `_nolock` サフィックス付きのバージョンは同じものですが、他のスレッドによる干渉から保護されない点が異なります。  他のスレッドをロックアウトするオーバーヘッドが発生しないため、処理が速くなる場合があります。  これらの関数は、シングルスレッド アプリケーション、呼び出し元のスコープで既にスレッド分離を処理している場合などのスレッドセーフなコンテキストでのみ使用してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_ungettch`|`_ungetch`|`_ungetch`|`_ungetwch`|  
|`_ungettch_nolock`|`_ungetch_nolock`|`_ungetch_nolock`|`_ungetwch_nolock`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_ungetch`, `_ungetch_nolock`|\<conio.h\>|  
|`_ungetwch`, `_ungetwch_nolock`|\<conio.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_ungetch.c  
// compile with: /c  
// In this program, a white-space delimited   
// token is read from the keyboard. When the program   
// encounters a delimiter, it uses _ungetch to replace   
// the character in the keyboard buffer.  
//  
  
#include <conio.h>  
#include <ctype.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char buffer[100];  
   int count = 0;  
   int ch;  
  
   ch = _getche();  
   while( isspace( ch ) )      // Skip preceding white space.  
      ch = _getche();  
   while( count < 99 )         // Gather token.  
   {  
      if( isspace( ch ) )      // End of token.  
         break;  
      buffer[count++] = (char)ch;  
      ch = _getche();  
   }  
   _ungetch( ch );            // Put back delimiter.  
   buffer[count] = '\0';      // Null terminate the token.  
   printf( "\ntoken = %s\n", buffer );  
}  
```  
  
  **`空白`トークン \= 空白**   
## 参照  
 [コンソール入出力とポート入出力](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cscanf、\_cscanf\_l、\_cwscanf、\_cwscanf\_l](../../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)   
 [\_getch、\_getwch](../Topic/_getch,%20_getwch.md)