---
title: "_pgmptr、_wpgmptr | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pgmptr"
  - "_pgmptr"
  - "wpgmptr"
  - "_wpgmptr"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_pgmptr 関数"
  - "_wpgmptr 関数"
  - "pgmptr 関数"
  - "wpgmptr 関数"
ms.assetid: 4d44b515-0eff-4136-8bc4-684195f218f5
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _pgmptr、_wpgmptr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

実行可能ファイルのパスです。  推奨される; [\_get\_pgmptr](../c-runtime-library/reference/get-pgmptr.md) と [\_get\_wpgmptr](../c-runtime-library/reference/get-wpgmptr.md)を使用します。  
  
## 構文  
  
```  
extern char *_pgmptr;  
extern wchar_t *_wpgmptr;  
```  
  
## 解説  
 プログラムがコマンド インタープリター \(Cmd.exe\) から実行する場合、`_pgmptr` は実行可能ファイルへの完全パスに自動的に初期化されます。  たとえば、Hello.exe が C:\\BIN にある C:\\BIN がパスに存在する場合、`_pgmptr` は C:\\BIN\\Hello.exe に実行するときに設定され、P:  
  
```  
C> hello   
```  
  
 プログラムをコマンド ラインから実行する場合、`_pgmptr` はプログラム名 \(ファイル名拡張子のないファイルの基本名\)、ファイル名、相対パス、完全パスで初期化される場合があります。  
  
 `_wpgmptr` は `wmain`を使用するプログラムの `_pgmptr` のワイド文字に相当します。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|  
  
## 必要条件  
  
|変数|必須ヘッダー|  
|--------|------------|  
|`_pgmptr`, `_wpgmptr`|\<stdlib.h\>|  
  
## 使用例  
 次のプログラムは `_pgmptr`の使用方法を示します。  
  
```  
// crt_pgmptr.c  
// compile with: /W3  
// The following program demonstrates the use of _pgmptr.  
//  
#include <stdio.h>  
#include <stdlib.h>  
int main( void )  
{  
   printf("The full path of the executing program is : %Fs\n",   
     _pgmptr); // C4996  
   // Note: _pgmptr is deprecated; use _get_pgmptr instead  
}  
```  
  
 `%S` へ `%Fs` と `wmain`へ `main` を変更することで `_wpgmptr` を使用できます。  
  
## 参照  
 [グローバル変数](../c-runtime-library/global-variables.md)