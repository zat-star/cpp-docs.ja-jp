---
title: "_callnewh | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_callnewh"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_callnewh"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_callnewh"
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# _callnewh
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在インストールされている*新しいハンドラー*を呼び出します。  
  
## 構文  
  
```cpp  
int _callnewh(  
   size_t size  
   )  
  
```  
  
#### パラメーター  
 `size`  
 [new 演算子](../../cpp/new-operator-cpp.md)が割り当てようとするメモリの量。  
  
## 戻り値  
  
|値|説明|  
|-------|--------|  
|0|エラー: 新しいハンドラーがインストールされていないか、新しいハンドラーがアクティブになっていません。|  
|1|成功: 新しいハンドラーがインストールされ、アクティブになっています。  メモリ割り当てを再試行できます。|  
  
## 例外  
 この関数は、*新しいハンドラー*が見つからない場合、[bad\_alloc](../../standard-library/bad-alloc-class.md) をスローします。  
  
## 解説  
 *新しいハンドラー*は、[new 演算子](../../cpp/new-operator-cpp.md)が正常なメモリの割り当てに失敗した場合に呼び出されます。  新しいハンドラーは、後続の割り当てが成功するようにメモリを解放するなど、適切な処理を開始する場合があります。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|\_callnewh|internal.h|  
  
## 参照  
 [\_set\_new\_handler](../Topic/_set_new_handler.md)   
 [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md)