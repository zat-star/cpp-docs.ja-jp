---
title: "_lock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lock"
apilocation: 
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcrt.dll"
  - "msvcr120_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "lock"
  - "_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lock 関数"
  - "_lock 関数"
ms.assetid: 29f77c37-30de-4b3d-91b6-030216e645a6
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# _lock
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

マルチスレッドのロックを取得します。  
  
> [!IMPORTANT]
>  これは古い関数です。 Visual Studio 2015 以降では、CRT で使用できません。  
  
## 構文  
  
```  
void __cdecl _lock  
   int locknum  
);  
```  
  
#### パラメーター  
 \[入力\] `locknum`  
 取得するロックの識別子。  
  
## 解説  
 ロックが既に取得されている場合は、このメソッドによってあらためてロックが取得され、内部 C ランタイム \(CRT\) エラーが発生します。 メソッドでロックを取得できない場合は、致命的なエラーで終了し、エラー コードが `_RT_LOCK` に設定されます。  
  
## 必要条件  
 **ソース:** mlock.c  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [\_unlock](../Topic/_unlock.md)