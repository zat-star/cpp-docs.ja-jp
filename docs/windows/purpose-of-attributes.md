---
title: "Purpose of Attributes | Microsoft Docs"
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
  - "attributes [C++], about attributes"
ms.assetid: 3aff8bfa-a2a3-4fcb-a2c6-1d96a2b4c68d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Purpose of Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

属性は言語の標準的な構造を現在中断できない方向の C\+\+ の機能を拡張します。  言語機能を動的に拡張する属性値を別のプロバイダー \(DLL\)。  属性の主な目的はコンポーネント開発者のレベルの生産性を向上させるだけでなく COM コンポーネントの作成には簡単にするためです。  属性クラスはデータ メンバーまたはメンバー関数などほとんどの C\+\+ 構成要素に適用できます。  次にこの新しいテクノロジが提供する利点を強調表示する :  
  
-   使い慣れた単純な呼び出し規約を公開します。  
  
-   ではマクロとは異なりデバッガーによって認識されるコードを挿入します。  
  
-   異常な実装の詳細なしで簡単な基本クラスからの派生ができます。  
  
-   COM コンポーネントで必要な数の簡単な属性で大量の IDL コードに置き換えます。  
  
 たとえば一般的な ATL クラスの単純なイベント シンクを実行するには`CMyReceiver` など特定のクラスに [event\_receiver](../windows/event-receiver.md) 属性を適用できます。  **event\_receiver** の属性はオブジェクト ファイルに適切なコードを挿入して Visual C\+\+ コンパイラでコンパイルします。  
  
```  
[event_receiver(com)]  
class CMyReceiver   
{  
   void handler1(int i) { ... }  
   void handler2(int i, float j) { ... }  
}  
```  
  
 作成できるイベント ソースからのイベントを処理するには**CMyReceiver** のメソッド `handler1` と `handler2` \(組み込み関数 [\_\_hook](../cpp/hook.md) を使用して設定できます。[ソース](../windows/event-source.md) を使用します。  
  
## 参照  
 [Concepts](../windows/attributed-programming-concepts.md)