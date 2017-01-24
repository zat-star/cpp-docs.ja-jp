---
title: "concurrent_priority_queue クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concurrent_priority_queue/concurrency::concurrent_priority_queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_priority_queue クラス"
ms.assetid: 3e740381-0f4e-41fc-8b66-ad0bb55f17a3
caps.latest.revision: 9
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# concurrent_priority_queue クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`concurrent_priority_queue` クラスは、複数のスレッドが項目を同時にプッシュおよびポップできるようにするコンテナーです。  項目は優先順位の順にポップされます。この優先順位は、テンプレート引数として指定されたファンクタによって決まります。  
  
## 構文  
  
```  
template <  
   typename _Ty,  
   typename _Compare=std::less<_Ty>,  
   typename _Ax = std::allocator<_Ty>  
>  
, typename _Ax = std::allocator<_Ty> > class concurrent_priority_queue;  
```  
  
#### パラメーター  
 `_Ty`  
 優先順位キューに格納される要素のデータ型。  
  
 `_Compare`  
 優先順位キューの相対順序を決定するためには、並べ替えキーとして 2 要素の値を比較する関数オブジェクトの型。  この引数は省略可能であり、既定値は二項述語 `less<``_Ty``>` です。  
  
 `_Ax`  
 並列優先順位キューのメモリの割り当てと解放に関する詳細をカプセル化する、格納されたアロケーター オブジェクトを表す型。  このオプションを省略すると、既定値は `allocator<``_Ty``>` になります。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`allocator_type`|並列優先順位キューのアロケーター クラスを表す型。|  
|`const_reference`|型の要素への定数参照を表す型は並列優先順位キューに格納します。|  
|`reference`|型の要素への参照を表す型は並列優先順位キューに格納します。|  
|`size_type`|並列優先順位キューの要素数をカウントする型。|  
|`value_type`|データ型を表す型は並列優先順位キューに格納します。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[concurrent\_priority\_queue::concurrent\_priority\_queue コンストラクター](../Topic/concurrent_priority_queue::concurrent_priority_queue%20Constructor.md)|オーバーロードされます。  並列優先順位キューを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[concurrent\_priority\_queue::clear メソッド](../Topic/concurrent_priority_queue::clear%20Method.md)|並列優先度のすべての要素を消去します。  このメソッドは同時実行セーフではありません。|  
|[concurrent\_priority\_queue::empty メソッド](../Topic/concurrent_priority_queue::empty%20Method.md)|並列優先順位キューがその時点で空のテストでは、このメソッドが呼び出されます。  このメソッドは同時実行セーフです。|  
|[concurrent\_priority\_queue::get\_allocator メソッド](../Topic/concurrent_priority_queue::get_allocator%20Method.md)|並列優先順位キューの構築に使用されるアロケーターのコピーを返します。  このメソッドは同時実行セーフです。|  
|[concurrent\_priority\_queue::push メソッド](../Topic/concurrent_priority_queue::push%20Method.md)|オーバーロードされます。  並列優先順位キューに要素を追加します。  このメソッドは同時実行セーフです。|  
|[concurrent\_priority\_queue::size メソッド](../Topic/concurrent_priority_queue::size%20Method.md)|並列優先順位キューの要素数を返します。  このメソッドは同時実行セーフです。|  
|[concurrent\_priority\_queue::swap メソッド](../Topic/concurrent_priority_queue::swap%20Method.md)|2 個の並列優先順位キューの内容を交換します。  このメソッドは同時実行セーフではありません。|  
|[concurrent\_priority\_queue::try\_pop メソッド](../Topic/concurrent_priority_queue::try_pop%20Method.md)|キューが空であるキューから優先順位の要素を削除して返します。  このメソッドは同時実行セーフです。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[concurrent\_priority\_queue::operator\= 演算子](../Topic/concurrent_priority_queue::operator=%20Operator.md)|オーバーロードされます。  別の `concurrent_priority_queue` オブジェクトの内容をこのオブジェクトに割り当てます。  このメソッドは同時実行セーフではありません。|  
  
## 解説  
 `concurrent_priority_queue` クラスの詳細については、「[並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)」を参照してください。  
  
## 継承階層  
 `concurrent_priority_queue`  
  
## 必要条件  
 **ヘッダー:** concurrent\_priority\_queue.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)