---
title: "stdin、stdout、stderr | Microsoft Docs"
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
  - "stdin"
  - "stderr"
  - "stdout"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "標準エラー ストリーム"
  - "標準入力ストリーム"
  - "標準出力ストリーム"
  - "stderr 関数"
  - "stdin 関数"
  - "stdout 関数"
ms.assetid: badd4735-596d-4498-857c-ec8b7e670e4c
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# stdin、stdout、stderr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
      FILE *stdin;   
FILE *stdout;   
FILE *stderr;   
#include <stdio.h>  
```  
  
## 解説  
 これらは、入力と出力、およびエラー出力の標準ストリームです。  
  
 既定ではキーボードから、標準入力標準出力と標準エラーは画面に出力されるが、読み取られます。  
  
 次のストリーム ポインターは標準ストリームにアクセスして使用する:  
  
|ポインター|Stream|  
|-----------|------------|  
|`stdin`|標準入力|  
|**stdout**|標準出力|  
|`stderr`|標準エラー|  
  
 これらのポインターは、関数の引数として使用できます。  一部の関数は、**getchar** と `putchar`など、`stdin` と **stdout** を自動的に使用します。  
  
 これらのポインター定数で、新しい値を割り当てることはできません。  `freopen` 関数がディスク ファイルまたはそのほかのデバイスにストリームをリダイレクトするために使用できます。  オペレーティング システムは、コマンド レベルでプログラミング標準の出力をリダイレクトすることができます。  
  
## 参照  
 [ストリーム入出力](../c-runtime-library/stream-i-o.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)