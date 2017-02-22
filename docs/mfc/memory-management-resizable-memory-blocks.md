---
title: "メモリ管理 : サイズ変更可能なメモリ ブロック | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ブロック, メモリの割り当て"
  - "メモリの割り当て, メモリ ブロック サイズ"
  - "メモリ ブロック, 割り当て"
  - "メモリ ブロック, サイズ変更可能"
  - "メモリ, 破損"
  - "サイズ変更可能なメモリ ブロック"
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# メモリ管理 : サイズ変更可能なメモリ ブロック
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

記事 [メモリ管理: 例](../mfc/memory-management-examples.md)で説明されている **new** と **delete** の演算子は、固定サイズのメモリ ブロックとオブジェクトを割り当ておよび解放するために便利です。  場合によっては、アプリケーションでサイズ変更可能なメモリ ブロックが必要な場合があります。  ヒープのサイズ変更可能メモリ ブロックを管理するために標準の C ランタイム ライブラリ関数 [malloc](../c-runtime-library/reference/malloc.md)、[realloc](../c-runtime-library/reference/realloc.md)と [free](../c-runtime-library/reference/free.md) を使用する必要があります。  
  
> [!IMPORTANT]
>  メモリ ブロックのサイズ変更可能メモリ割り当て関数と **new** と **delete** の演算子を使用すると、MFC のデバッグ バージョンでメモリ破損が発生します。  **new**に割り当てられたメモリ ブロックの `realloc` を使用しないでください。  同様に、**new** の演算子を使用してメモリ ブロックを割り当て、**free**に削除する必要があります。または `malloc`に割り当てられたメモリ ブロックの **delete** の演算子を使用します。  
  
## 参照  
 [メモリ管理 : ヒープ割り当て](../mfc/memory-management-heap-allocation.md)