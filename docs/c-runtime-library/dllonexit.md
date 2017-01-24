---
title: "__dllonexit | Microsoft Docs"
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
  - "__dllonexit"
apilocation: 
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr120_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__dllonexit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__dllonexit"
ms.assetid: 708f2ceb-f95c-46b0-a58d-d68b3fa36f12
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __dllonexit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

終了時に呼び出されるルーチンを登録します。  
  
## 構文  
  
```  
_onexit_t __dllonexit(  
   _onexit_t func,  
   _PVFV **  pbegin,   
   _PVFV **  pend   
   )  
```  
  
#### パラメーター  
 `func`  
 終了時に実行する関数へのポインター。  
  
 `pbegin`  
 この関数のリストの先頭を実行する変数へのポインターはデタッチを指します。  
  
 `pend`  
 その変数へのポインターは、関数のリストの最後の実行にデタッチを指します。  
  
## 戻り値  
 関数ポインター、ユーザーに成功した。  それ以外の場合は Null ポインター。  
  
## 解説  
 `__dllonexit` 関数は [\_onexit](../c-runtime-library/reference/onexit-onexit-m.md) 関数に似ていますが、この関数によって使用されるグローバル変数がこのルーチンに表示されません。  グローバル変数の代わりに、この関数は `pbegin` と `pend` パラメーターを使用します。  
  
 MSVCRT.LIB とリンクする DLL の `_onexit` と `atexit` 関数は独自の atexit\/\_onexit のリストを保持する必要があります。  このルーチンは、このような DLL によって呼び出されるワーカーです。  
  
 `_PVFV` の型は `typedef void (__cdecl *_PVFV)(void)`として定義されます。  
  
## 必要条件  
  
|ルーチン|必須ファイル|  
|----------|------------|  
|\_\_dllonexit|onexit.c|  
  
## 参照  
 [\_onexit、\_onexit\_m](../c-runtime-library/reference/onexit-onexit-m.md)