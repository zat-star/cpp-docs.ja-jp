---
title: "メモリ管理 | Microsoft Docs"
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
  - "メモリ"
  - "メモリの割り当て"
  - "メモリの割り当て, MFC"
  - "メモリ, 管理"
  - "MFC, メモリ管理"
ms.assetid: 934ac81b-d630-4232-88e5-ea74f7187987
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# メモリ管理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

記事のグループは、メモリ管理に関連する Microsoft Foundation Class ライブラリ \(MFC\) の汎用サービスを利用する方法について説明します。  メモリ割り当ては 2 個の主要カテゴリに分類できます。: フレームの割り当ておよびヒープ割り当て。  
  
 2 個の割り当て方法の間の 1 種類の主な違いは、ヒープ割り当てとメモリ ブロックへのポインターが常に指定が、実際のメモリ ブロック自体を使用するフレームの割り当てと区別することができません。  2 種類の方法で別の主な違いは、ヒープ オブジェクトは、プログラマによって明示的に削除する必要があります。フレーム オブジェクトが自動的に削除されることです。  
  
 Windows のプログラムのメモリ管理の非 MFC の詳細については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の [メモリ管理](http://msdn.microsoft.com/library/windows/desktop/aa366779) を参照してください。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [割り当てを構築します。](../mfc/memory-management-frame-allocation.md)  
  
-   [ヒープ割り当て](../mfc/memory-management-heap-allocation.md)  
  
-   [配列にメモリを割り当てます。](../mfc/memory-management-examples.md)  
  
-   [ヒープからの配列のメモリの解放](../mfc/memory-management-examples.md)  
  
-   [データ構造のメモリを割り当てます。](../mfc/memory-management-examples.md)  
  
-   [オブジェクトにメモリを割り当てます。](../mfc/memory-management-examples.md)  
  
-   [サイズ変更可能なメモリ ブロック](../mfc/memory-management-resizable-memory-blocks.md)  
  
## 参照  
 [概念](../mfc/mfc-concepts.md)   
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)