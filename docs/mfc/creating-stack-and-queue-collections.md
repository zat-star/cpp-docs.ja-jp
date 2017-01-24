---
title: "スタック コレクションとキュー コレクションの作成 | Microsoft Docs"
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
helpviewer_keywords: 
  - "コレクション クラス, 作成"
  - "コレクション, キュー"
  - "コレクション, スタック"
  - "MFC コレクション クラス, キューのコレクション"
  - "MFC コレクション クラス, スタック コレクション"
  - "キューのコレクション"
  - "スタック"
  - "スタック コレクション"
ms.assetid: 3c7bc198-35f0-4fc3-aaed-6005a0f22638
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# スタック コレクションとキュー コレクションの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、別のデータ構造体は、MFC のリスト クラスから [スタック](#_core_stacks) と [キュー](#_core_queues)など\) を作成する方法について説明します。  例では `CList`から派生されるクラスを使用して機能を追加する必要がある `CList` を直接使用できます。  
  
##  <a name="_core_stacks"></a> スタック  
 標準リスト コレクションにヘッダーと末尾の両方を持つため、後入れ先出し \(LIFO\) スタックの動作を模倣する派生リストのコレクションを作成する方が簡単です。  スタックはカフェテリアのトレイにスタックに似ています。  トレイがスタックに追加される場合、スタックの一番上をクリックします。  追加された最後のトレイは削除する 1 番目のチュートリアルです。  リスト コレクションのメンバー関数 `AddHead` と `RemoveHead` がリストの先頭にある要素を追加および削除するために使用できます。; したがって、最後に追加する要素は、1 番目の排除されます。  
  
#### スタック コレクションを作成するには  
  
1.  新しいリスト クラスを既存の MFC リスト クラスの 1 つがから派生し、スタック操作機能をサポートするためのメンバー関数を追加します。  
  
     次の例では、メンバー関数をプッシュ要素にスタックに追加し、スタックの最上位の要素を表示します。表示、スタックの最上位の要素をポップする方法を示しています。:  
  
     [!code-cpp[NVC_MFCCollections#20](../mfc/codesnippet/CPP/creating-stack-and-queue-collections_1.h)]  
  
 この方法は `CObList` の基本クラスを公開していることに注意してください。  ユーザーはの意味をスタック適切かどうか `CObList` のメンバー関数を呼び出すことができます。  
  
##  <a name="_core_queues"></a> キュー  
 標準リスト コレクションにヘッダーと末尾の両方を持つため、先入れ先出しキューの動作を模倣する派生リストのコレクションを作成することも簡単です。  キューがカフェテリアの個人の行に表示されます。  行の最初の人が実行される 1 番目のチュートリアルです。  より多くのユーザーを受け取るように回転を待機することを、行の末尾に移動します。  リスト コレクションのメンバー関数 `AddTail` と `RemoveHead` がリストの先頭または末尾の要素を追加および削除するために使用できます。; したがって、最近追加された要素が削除されている場合は、最後に常になります。  
  
#### キューのコレクションを作成するには  
  
1.  新しいリスト クラスを Microsoft Foundation Class ライブラリに用意されている定義済みのなリスト クラスの 1 つがから派生し、キュー操作のセマンティクスをサポートするためのメンバー関数を追加します。  
  
     要素をキューの末尾に追加し、キューの頭から要素を取得するようにメンバー関数を追加する方法を次の例に示します。  
  
     [!code-cpp[NVC_MFCCollections#21](../mfc/codesnippet/CPP/creating-stack-and-queue-collections_2.h)]  
  
## 参照  
 [コレクション クラス](../mfc/collections.md)