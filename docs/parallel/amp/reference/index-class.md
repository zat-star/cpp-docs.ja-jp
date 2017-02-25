---
title: "index クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::index"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "インデックス構造体"
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# index クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

*N* 次元のインデックス位置を定義します。  
  
## 構文  
  
```  
template <  
   int _Rank  
>  
class index;  
```  
  
#### パラメーター  
 `_Rank`  
 ランク \(次元数\)。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[index::index コンストラクター](../Topic/index::index%20Constructor.md)|`index` クラスの新しいインスタンスを初期化します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[index::operator\-\- 演算子](../Topic/index::operator--%20Operator.md)|`index` オブジェクトの各要素をデクリメントします。|  
|[index::operator\(mod\)\= 演算子](../Topic/index::operator\(mod\)=%20Operator.md)|その要素がある数で除算された場合、`index` オブジェクトの各要素の剰余を計算します。|  
|[index::operator\*\= 演算子](../Topic/index::operator*=%20Operator.md)|`index` オブジェクトの各要素をある数で乗算します。|  
|[index::operator\/\= 演算子](../Topic/index::operator-=%20Operator2.md)|`index` オブジェクトの各要素をある数で除算します。|  
|[index::operatorOperator](../Topic/index::operatorOperator.md)|指定したインデックス位置にある要素を返します。|  
|[index::operator\+\+ 演算子](../Topic/index::operator++%20Operator.md)|`index` オブジェクトの各要素をインクリメントします。|  
|[index::operator\+\= 演算子](../Topic/index::operator+=%20Operator.md)|指定した数を `index` オブジェクトの各要素に加算します。|  
|[index::operator\= 演算子](../Topic/index::operator=%20Operator.md)|指定された `index` オブジェクトの内容をこのオブジェクトにコピーします。|  
|[index::operator\-\= 演算子](../Topic/index::operator-=%20Operator1.md)|指定した数を `index` オブジェクトの各要素から減算します。|  
  
### パブリック定数  
  
|名前|説明|  
|--------|--------|  
|[index::rank 定数](../Topic/index::rank%20Constant.md)|`index` オブジェクトのランクを格納します。|  
  
## 継承階層  
 `index`  
  
## 解説  
 `index` 構造体は、*N* 次元の空間の一意の場所を指定する *N* 整数の座標ベクターを表します。  ベクターの値は最上位から最下位へ順に並べ替えられます。  [index::operator\= 演算子](../Topic/index::operator=%20Operator.md) を使用して、コンポーネントの値を取得できます。  
  
## 必要条件  
 **ヘッダー:** amp.h  
  
 **名前空間:** Concurrency  
  
## 参照  
 [Concurrency 名前空間 \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)