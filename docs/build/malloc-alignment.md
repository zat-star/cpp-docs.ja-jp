---
title: "malloc アライメント | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: a8d1d1b4-5122-456f-9a64-a50e105e55a5
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# malloc アライメント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[malloc](../c-runtime-library/reference/malloc.md) は、オブジェクトが基本的なアラインメントに従い、割り当てられたメモリ量の限度で格納できる限り、どのようなオブジェクトを格納する場合でも適切なアラインメントのメモリを返すことを保証します。  *基本的なアラインメント*とは、アラインメントを指定せずに実装によってサポートされる最大のアラインメントを上限とするアラインメントです \(Visual C\+\+ の基本的なアラインメントは、`double` つまり 8 バイトに対して必要なアラインメントです。  In code that targets 64\-bit platforms, it’s 16 bytes.\)たとえば、4 バイト割り当ての場合、4 バイト以下のオブジェクトをサポートする境界上にアラインメントされます。  
  
 Visual C\+\+ では、*拡張アラインメント*を持つ型が許可されています。これは別名、*オーバーアラインメント*型とも呼ばれます。  たとえば、SSE 型の [\_\_m128](../Topic/__m128.md) や `__m256`、また `__declspec(align(``n``))` で、`n` に 8 を超える数値を設定して宣言した型などです。  オブジェクトで拡張アラインメントが必要な場合、そのオブジェクトに適した境界上でのメモリのアラインメントは、`malloc` によって保証されません。  オーバーアラインメント型にメモリを割り当てるには、[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) とその関連の関数を使用します。  
  
## 参照  
 [スタックの使用](../build/stack-usage.md)   
 [align](../cpp/align-cpp.md)   
 [\_\_declspec](../cpp/declspec.md)