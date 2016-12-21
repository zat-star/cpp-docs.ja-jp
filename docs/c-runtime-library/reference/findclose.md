---
title: "_findclose | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_findclose"
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
  - "_findclose"
  - "findclose"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_findclose 関数"
  - "findclose 関数"
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _findclose
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定した検索ハンドルを閉じ、関連付けられたリソースを解放します。  
  
## 構文  
  
```  
int _findclose(   
   intptr_t handle   
);  
```  
  
#### パラメーター  
 `handle`  
 `_findfirst`に前の呼び出しによって返される検索ハンドル。  
  
## 戻り値  
 `_findclose`、正常終了した場合は 0 を返します。  それ以外の場合は–1 を返し、一致するファイルが見つからなかったことを示す `ENOENT`に `errno` を設定します。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`_findclose`|\<io.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [システム コール](../Topic/System%20Calls.md)   
 [ファイル名検索関数](../../c-runtime-library/filename-search-functions.md)