---
title: "_heapset | Microsoft Docs"
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
  - "_heapset"
apilocation: 
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcrt.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_heapset"
  - "heapset"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_heapset 関数"
  - "チェック (ヒープを)"
  - "デバッグ [CRT], ヒープ関連の問題"
  - "ヒープ, チェック"
  - "heapset 関数"
ms.assetid: 9667eeb0-55bc-4c19-af5f-d1fd0a142b3c
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _heapset
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ヒープの最小限の一貫性をチェックし、空きエントリを指定した値に設定します。  
  
> [!IMPORTANT]
>  これは古い関数です。 Visual Studio 2015 以降、CRT で使用できません。  
  
## 構文  
  
```  
int _heapset(   
   unsigned int fill   
);  
```  
  
#### パラメーター  
 `fill`  
 充填文字。  
  
## 戻り値  
 `_heapset` は、Malloc.h に定義されている次の整数のマニフェスト定数のいずれかを返します。  
  
 `_HEAPBADBEGIN`  
 初期ヘッダー情報が無効または見つかりません。  
  
 `_HEAPBADNODE`  
 ヒープが破損しているか、不適切なノードが見つかりました。  
  
 `_HEAPEMPTY`  
 ヒープが初期化されていません。  
  
 `_HEAPOK`  
 ヒープは一貫性があると思われます。  
  
 また、エラーが発生した場合、`_heapset` は `errno` を `ENOSYS` に設定します。  
  
## 解説  
 `_heapset` 関数は、誤って上書きされた空きメモリの場所またはノードを示します。  
  
 `_heapset` は、ヒープの最小限の一貫性をチェックし、ヒープの空きエントリの各バイトに `fill` 値を設定します。 この既知の値は、空きノードがあるヒープのメモリ位置を示すとともに、解放されたメモリに誤って書き込まれたデータを含むのはどれかを示します。 オペレーティング システムで `_heapset`がサポートされていない場合 \(たとえば、Windows 98\)、この関数は `_HEAPOK` を返し、`errno` を `ENOSYS` に設定します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|----------|------------|----------------|  
|`_heapset`|\<malloc.h\>|\<errno.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_heapset.c // This program checks the heap and // fills in free entries with the character 'Z'. #include <malloc.h> #include <stdio.h> #include <stdlib.h> int main( void ) { int heapstatus; char *buffer; if( (buffer = malloc( 1 )) == NULL ) // Make sure heap is exit( 0 );                        //    initialized heapstatus = _heapset( 'Z' );        // Fill in free entries switch( heapstatus ) { case _HEAPOK: printf( "OK - heap is fine\n" ); break; case _HEAPEMPTY: printf( "OK - heap is empty\n" ); break; case _HEAPBADBEGIN: printf( "ERROR - bad start of heap\n" ); break; case _HEAPBADNODE: printf( "ERROR - bad node in heap\n" ); break; } free( buffer ); }  
```  
  
```Output  
OK - ヒープは正常です  
```  
  
## 同等の .NET Framework 関数  
 該当しない。 標準 C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [メモリ割り当て](../c-runtime-library/memory-allocation.md)   
 [\_heapadd](../c-runtime-library/heapadd.md)   
 [\_heapchk](../c-runtime-library/reference/heapchk.md)   
 [\_heapmin](../c-runtime-library/reference/heapmin.md)   
 [\_heapwalk](../Topic/_heapwalk.md)