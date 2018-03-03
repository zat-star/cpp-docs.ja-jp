---
title: "メモリ管理: サイズ変更可能なメモリ ブロック |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- memory blocks [MFC], resizable
- memory [MFC], corruption
- memory allocation [MFC], memory block size
- memory blocks [MFC], allocating
- blocks [MFC], memory allocation
- resizable memory blocks [MFC]
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3fce06d27a091ad1740c882367358cf69a6dc3e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="memory-management-resizable-memory-blocks"></a>メモリ管理 : サイズ変更可能なメモリ ブロック
**新しい**と**削除**演算子、資料に記載[メモリ管理: 例](../mfc/memory-management-examples.md)、割り当てと固定サイズのメモリ ブロックを解放するのに適しているとオブジェクト。 場合によっては、アプリケーションには、サイズ変更可能なメモリ ブロックが必要があります。 標準の C ランタイム ライブラリ関数を使用する必要があります[malloc](../c-runtime-library/reference/malloc.md)、 [realloc](../c-runtime-library/reference/realloc.md)、および[空き](../c-runtime-library/reference/free.md)ヒープのサイズ変更可能なメモリ ブロックを管理します。  
  
> [!IMPORTANT]
>  混合、**新しい**と**削除**同じメモリ ブロックのサイズ変更可能なメモリを割り当てる関数と演算子は、MFC のデバッグ バージョンでメモリの破損になります。 使用しないで`realloc`で割り当てられたメモリ ブロックに**新しい**です。 同様に、割り当てる必要がありますいないメモリ ブロックを**新しい**演算子で、削除して**空き**を使用して、または、**削除**で割り当てられたメモリブロックの演算子`malloc`.  
  
## <a name="see-also"></a>参照  
 [メモリ管理: ヒープ割り当て](../mfc/memory-management-heap-allocation.md)

