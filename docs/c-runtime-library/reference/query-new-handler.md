---
title: "_query_new_handler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_query_new_handler"
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
  - "_query_new_handler"
  - "query_new_handler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_query_new_handler 関数"
  - "エラー処理"
  - "ハンドラー ルーチン"
  - "query_new_handler 関数"
ms.assetid: 9a84b5c3-fe33-4c01-83a0-be87dc3ec518
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# _query_new_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在の new ハンドラー ルーチンのアドレスを返します。  
  
## 構文  
  
```  
  
      _PNH _query_new_handler(  
   void   
);  
```  
  
## 戻り値  
 現在の new ハンドラー ルーチンのアドレスを `_set_new_handler`に設定して返します。  
  
## 解説  
 C\+\+ `_query_new_handler` 関数の戻り値 [\_set\_new\_handler](../Topic/_set_new_handler.md) C\+\+ 関数による現在の例外処理関数のアドレス。  `_set_new_handler` が メモリの割り当て **new** の演算子がしないコントロールを取得するときに、例外処理関数を指定するために使用されます。  詳細については、" *C\+\+ Language Reference*" [新しい演算子](../../misc/operator-new-function.md) と [演算子の削除](../Topic/operator%20delete%20Function.md) 関数の説明を参照します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_query_new_handler`|\<new.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)