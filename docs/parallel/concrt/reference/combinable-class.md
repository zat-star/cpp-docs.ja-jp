---
title: "combinable クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppl/concurrency::combinable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "combinable クラス"
ms.assetid: fe0bfbf6-6250-47da-b8d0-f75369f0b5be
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# combinable クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`combinable<T>` オブジェクトは、スレッド プライベートなデータのコピーを提供し、並列アルゴリズムにおいてロック制御不要なスレッド ローカルのサブ計算を実行するために用意されています。  並列操作の最後に、スレッド プライベート サブ計算を最終結果に結合できます。  共有変数に多数の競合が発生する可能性がある場合、共有変数の代わりにこのクラスを使用することにより、パフォーマンスを改善できます。  
  
## 構文  
  
```  
template<  
   typename _Ty  
>  
class combinable;  
```  
  
#### パラメーター  
 `_Ty`  
 結合された最終結果のデータ型。  この型には、コピー コンストラクターおよび既定のコンストラクターが必要です。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[combinable::combinable コンストラクター](../Topic/combinable::combinable%20Constructor.md)|オーバーロードされます。  新しい `combinable` オブジェクトを構築します。|  
|[combinable::~combinable デストラクター](../Topic/combinable::~combinable%20Destructor.md)|`combinable` オブジェクトを破棄します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[combinable::clear メソッド](../Topic/combinable::clear%20Method.md)|前回の使用で得た中間の計算結果を消去します。|  
|[combinable::combine メソッド](../Topic/combinable::combine%20Method.md)|指定された結合ファンクタを呼び出して、スレッド ローカル サブ計算のセットから最終値を計算します。|  
|[combinable::combine\_each メソッド](../Topic/combinable::combine_each%20Method.md)|指定された結合ファンクタをスレッド ローカル サブ計算ごとに 1 回ずつ呼び出して、スレッド ローカル サブ計算のセットから最終値を計算します。  最終結果の累積計算は関数オブジェクトによって行われます。|  
|[combinable::local メソッド](../Topic/combinable::local%20Method.md)|オーバーロードされます。  スレッド プライベート サブ計算への参照を返します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[combinable::operator\= 演算子](../Topic/combinable::operator=%20Operator.md)|別の `combinable` オブジェクトから `combinable` オブジェクトに代入します。|  
  
## 解説  
 詳細については、「[並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)」を参照してください。  
  
## 継承階層  
 `combinable`  
  
## 必要条件  
 **ヘッダー:** ppl.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)