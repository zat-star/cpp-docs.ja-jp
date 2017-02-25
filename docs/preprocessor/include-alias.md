---
title: "include_alias | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.include_alias"
  - "include_alias_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "include_alias プラグマ"
  - "プラグマ, include_alias"
ms.assetid: 3256d589-12b3-4af0-a586-199e96eabacc
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# include_alias
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*short\_filename* を *long\_filename* のエイリアスとして使用することを指定します。  
  
## 構文  
  
```  
  
      #pragma include_alias( "  
      long_filename  
      ", "  
      short_filename  
      " )  
#pragma include_alias( <long_filename>, <short_filename> )  
```  
  
## 解説  
 一部のファイル システムでは、FAT ファイル システムの 8.3 制限よりも長いヘッダー ファイル名が許可されます。  長いヘッダー ファイル名の最初の 8 文字は一意でない可能性があるため、コンパイラは、長い名前を単純に 8.3 形式に切り詰めることはできません。  コンパイラは *long\_filename* 文字列を検出すると *short\_filename* に置き換え、ヘッダー ファイル *short\_filename* を代わりに検索します。  このプラグマは、対応する `#include` ディレクティブよりも前に記述する必要があります。  次に例を示します。  
  
```  
// First eight characters of these two files not unique.  
#pragma include_alias( "AppleSystemHeaderQuickdraw.h", "quickdra.h" )  
#pragma include_alias( "AppleSystemHeaderFruit.h", "fruit.h" )  
  
#pragma include_alias( "GraphicsMenu.h", "gramenu.h" )  
  
#include "AppleSystemHeaderQuickdraw.h"  
#include "AppleSystemHeaderFruit.h"  
#include "GraphicsMenu.h"  
```  
  
 検索するエイリアスは、大文字\/小文字、スペル、および二重引用符や山かっこの使い方が、指定と正確に一致する必要があります。  **include\_alias** プラグマは、ファイル名の単純な文字列照合を実行します。これ以外のファイル名の検証は実行されません。  たとえば、次のようなディレクティブがあるとします。  
  
```  
#pragma include_alias("mymath.h", "math.h")  
#include "./mymath.h"  
#include "sys/mymath.h"  
```  
  
 ヘッダー ファイル文字列が正確に一致しないため、エイリアシング \(置換\) は実行されません。  また、\/Yu および \/Yc コンパイラ オプションまたは **hdrstop** プラグマの引数として使用されるヘッダー ファイル名も置き換えられません。  たとえば、ソース ファイルに次のディレクティブが含まれている場合、  
  
```  
#include <AppleSystemHeaderStop.h>  
```  
  
 対応するコンパイラ オプションは、次のようになります。  
  
```  
/YcAppleSystemHeaderStop.h  
```  
  
 **include\_alias** プラグマを使用して、任意のヘッダー ファイル名を別のヘッダー ファイル名にマップすることができます。  次に例を示します。  
  
```  
#pragma include_alias( "api.h", "c:\version1.0\api.h" )  
#pragma include_alias( <stdio.h>, <newstdio.h> )  
#include "api.h"  
#include <stdio.h>  
```  
  
 二重引用符で囲んだファイル名と山かっこで囲んだファイル名を混同しないでください。  たとえば、前の 2 つの **\#pragma include\_alias** ディレクティブを指定すると、次の `#include` ディレクティブで置換は実行されません。  
  
```  
#include <api.h>  
#include "stdio.h"  
```  
  
 さらに、次のディレクティブはエラーになります。  
  
```  
#pragma include_alias(<header.h>, "header.h")  // Error  
```  
  
 エラー メッセージで報告されるファイル名、または定義済みの **\_\_FILE\_\_** マクロの値として報告されるファイル名は、置換実行後のファイル名であることに注意してください。  たとえば、次のディレクティブの後、  
  
```  
#pragma include_alias( "VeryLongFileName.H", "myfile.h" )  
#include "VeryLongFileName.H"  
```  
  
 VERYLONGFILENAME.H にエラーがあると、次のエラー メッセージが生成されます。  
  
```  
myfile.h(15) : error C2059 : syntax error  
```  
  
 また、推移もサポートされません。  次のようなディレクティブがあるとします。  
  
```  
#pragma include_alias( "one.h", "two.h" )  
#pragma include_alias( "two.h", "three.h" )  
#include "one.h"  
```  
  
 コンパイラは、THREE.H. ではなく、TWO.H ファイルを探します。  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)