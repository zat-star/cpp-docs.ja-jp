---
title: "_unlock_file | Microsoft Docs"
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
  - "_unlock_file"
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
  - "_unlock_file"
  - "unlock_file"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_unlock_file 関数"
  - "ファイル [C++], ロック解除"
  - "unlock_file 関数"
  - "ロック解除 (ファイルを)"
ms.assetid: cf380a51-6d3a-4f38-bd64-2d4fb57b4369
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _unlock_file
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルのロックを解除し、ファイルにアクセスする他のプロセスができます。  
  
## 構文  
  
```  
void _unlock_file(  
   FILE* file  
);  
```  
  
#### パラメーター  
 `file`  
 ファイル ハンドル。  
  
## 解説  
 `file`で指定された `_unlock_file` 関数はファイルのロックを解除します。  ファイルのロックを解除すると、他のプロセスによるファイルへのアクセスを可能にします。  この関数は `_lock_file` が前に `file` のポインター頼まれなかったら呼び出す必要があります。  ロックされていないファイルの `_unlock_file` を呼び出すと、デッドロックが発生することがあります。  例については、「[\_lock\_file](../Topic/_lock_file.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_unlock_file`|\<stdio.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::IO::FileStream::Lock](https://msdn.microsoft.com/en-us/library/system.io.filestream.lock.aspx)  
  
## 参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [\_creat、\_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open、\_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_lock\_file](../Topic/_lock_file.md)