---
title: "_cscanf、_cscanf_l、_cwscanf、_cwscanf_l | Microsoft Docs"
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
  - "_cscanf_l"
  - "_cscanf"
  - "_cwscanf"
  - "_cwscanf_l"
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
apitype: "DLLExport"
f1_keywords: 
  - "_cwscanf"
  - "cwscanf_l"
  - "tcscanf_l"
  - "_tcscanf_l"
  - "_cscanf"
  - "_cscanf_l"
  - "tcscanf"
  - "cwscanf"
  - "_cwscanf_l"
  - "cscanf_l"
  - "_tcscanf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_cscanf 関数"
  - "_cscanf_l 関数"
  - "_cwscanf 関数"
  - "_cwscanf_l 関数"
  - "_tcscanf 関数"
  - "_tcscanf_l 関数"
  - "cscanf_l 関数"
  - "cwscanf 関数"
  - "cwscanf_l 関数"
  - "データ [C++], 読み取り (コンソールから)"
  - "読み取り (データを) [C++], コンソールから"
  - "tcscanf 関数"
  - "tcscanf_l 関数"
ms.assetid: dbfe7547-b577-4567-a1cb-893fa640e669
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _cscanf、_cscanf_l、_cwscanf、_cwscanf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンソールから書式化されたデータを読み出します。  これらの関数のセキュリティを強化したバージョンについては、「[\_cscanf\_s、\_cscanf\_s\_l、\_cwscanf\_s、\_cwscanf\_s\_l](../../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)」を参照してください。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
int _cscanf(   
   const char *format [,  
   argument] ...   
);  
int _cscanf_l(   
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _cwscanf(   
   const wchar_t *format [,  
   argument] ...   
);  
int _cwscanf_l(   
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
```  
  
#### パラメーター  
 `format`  
 書式指定文字列。  
  
 `argument`  
 省略可能なパラメーター。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 正常に変換され、割り当てられたフィールドの数。  戻り値には、読まれたが割り当てられなかったフィールドは含まれません。  ファイルの終端で読み取ろうとした場合、戻り値は、`EOF` です。  これは、キーボード入力がオペレーティング システムのコマンド ラインのレベルでリダイレクトされる場合に発生します。  戻り値が 0 の場合は、代入されたフィールドがなかったことを意味します。  
  
## 解説  
 `_cscanf` 関数は、コンソールからデータを `argument` で指定した位置に直接読み込みます。  [\_getche](../Topic/_getch,%20_getwch.md) 関数は文字を読み取るために使用されます。  省略可能なパラメーターは、それぞれ、`format` の型指定子に対応する型の変数へのポインターにする必要があります。  format は、入力フィールドの解釈を制御し、[scanf](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) 関数の `format` パラメーターと同じ形式と機能を持ちます。  `_cscanf` は、通常、入力文字がエコーされますが、最後の呼び出しが `_ungetch` に対してである場合はエコーしません。  
  
 この関数は、パラメーターを検証します。  format が NULL の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、`errno` が `EINVAL` に設定され、関数から `EOF` が返されます。  
  
 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tcscanf`|`_cscanf`|`_cscanf`|`_cwscanf`|  
|`_tcscanf_l`|`_cscanf_l`|`_cscanf_l`|`_cwscanf_l`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_cscanf`,`_cscanf_l`|\<conio.h\>|  
|`_cwscanf`, `_cwscanf_l`|\<conio.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_cscanf.c  
// compile with: /c /W3  
/* This program prompts for a string  
 * and uses _cscanf to read in the response.  
 * Then _cscanf returns the number of items  
 * matched, and the program displays that number.  
 */  
  
#include <stdio.h>  
#include <conio.h>  
  
int main( void )  
{  
   int   result, i[3];  
  
   _cprintf_s( "Enter three integers: ");  
   result = _cscanf( "%i %i %i", &i[0], &i[1], &i[2] ); // C4996  
   // Note: _cscanf is deprecated; consider using _cscanf_s instead  
   _cprintf_s( "\r\nYou entered " );  
   while( result-- )  
      _cprintf_s( "%i ", i[result] );  
   _cprintf_s( "\r\n" );  
}  
```  
  
## 入力  
  
```  
1 2 3  
```  
  
## 出力  
  
```  
Enter three integers: 1 2 3  
You entered 3 2 1  
```  
  
## 参照  
 [コンソール入出力とポート入出力](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cprintf、\_cprintf\_l、\_cwprintf、\_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [fscanf、\_fscanf\_l、fwscanf、\_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [scanf\_s、\_scanf\_s\_l、wscanf\_s、\_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [sscanf、\_sscanf\_l、swscanf、\_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)