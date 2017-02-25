---
title: "&lt;valarray&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.<valarray>"
  - "valarray/std::<valarray>"
  - "std::<valarray>"
  - "<valarray>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "valarray ヘッダー"
ms.assetid: 30835415-21c1-4801-8f24-6bbef7dd8ecd
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# &lt;valarray&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

テンプレート クラス valarray、および多数のサポート テンプレート クラスと関数を定義します。  
  
## 構文  
  
```  
  
#include <valarray>  
  
```  
  
## 解説  
 これらのテンプレート クラスと関数には、パフォーマンス向上を目的として特別な許容度が認められています。  具体的には、**valarray\<**T1**\>** 型を返す関数はすべて、他の T2 型のオブジェクトを返すこともできます。  その場合、**valarray\<**T2**\>** 型の引数を受け取る関数すべてに、T2 型に置換された個々の引数が任意に組み合わされたものを受け取るオーバーロードが必要です。  
  
### Functions  
  
|||  
|-|-|  
|[abs](../Topic/abs%20\(%3Cvalarray%3E\).md)|入力 valarray の要素を演算し、入力 valarray の要素の絶対値と等しい要素を持つ valarray を返します。|  
|[acos](../Topic/acos%20\(%3Cvalarray%3E\).md)|入力 valarray の要素を演算し、入力 valarray の要素のアークコサインと等しい要素を持つ valarray を返します。|  
|[asin](../Topic/asin%20\(%3Cvalarray%3E\).md)|入力 valarray の要素を演算し、入力 valarray の要素のアークサインと等しい要素を持つ valarray を返します。|  
|[atan](../Topic/atan%20\(%3Cvalarray%3E\).md)|入力 valarray の要素を演算し、入力 valarray の要素のアークタンジェントの主値と等しい要素を持つ valarray を返します。|  
|[atan2](../Topic/atan2%20\(%3Cvalarray%3E\).md)|valarray の定数と要素の組み合わせによって指定されたデカルト成分のアークタンジェントと等しい要素を持つ valarray を返します。|  
|[cos](../Topic/cos%20\(%3Cvalarray%3E\).md)|入力 valarray の要素を演算し、入力 valarray の要素のコサインと等しい要素を持つ valarray を返します。|  
|[cosh](../Topic/cosh%20\(%3Cvalarray%3E\).md)|入力 valarray の要素を演算し、入力 valarray の要素のハイパーボリック コサインと等しい要素を持つ valarray を返します。|  
|[exp](../Topic/exp%20\(%3Cvalarray%3E\).md)|入力 valarray の要素を演算し、入力 valarray の要素の自然指数と等しい要素を持つ valarray を返します。|  
|[log](../Topic/log%20\(%3Cvalarray%3E\).md)|入力 valarray の要素を演算し、入力 valarray の要素の自然対数と等しい要素を持つ valarray を返します。|  
|[log10](../Topic/log10%20\(%3Cvalarray%3E\).md)|入力 valarray の要素を演算し、入力 valarray の要素の常用対数 \(底が 10 の対数\) と等しい要素を持つ valarray を返します。|  
|[pow](../Topic/pow%20\(%3Cvalarray%3E\).md)|入力 valarray と定数の要素を演算し、入力 valarray の要素によって指定されている底と等しい要素を持つ valarray か、入力 valarray か定数の要素で指定された値だけ定数を指数乗したものと等しい要素を持つ valarray を返します。|  
|[sin](../Topic/sin%20\(%3Cvalarray%3E\).md)|入力 valarray の要素を演算し、入力 valarray の要素のサインと等しい要素を持つ valarray を返します。|  
|[sinh](../Topic/sinh%20\(%3Cvalarray%3E\).md)|入力 valarray の要素を演算し、入力 valarray の要素のハイパーボリック サインと等しい要素を持つ valarray を返します。|  
|[sqrt](../Topic/sqrt%20\(%3Cvalarray%3E\).md)|入力 valarray の要素を演算し、入力 valarray の要素の平方根と等しい要素を持つ valarray を返します。|  
|[swap](../Topic/swap%20\(%3Cvalarray%3E\).md)||  
|[tan](../Topic/tan%20\(%3Cvalarray%3E\).md)|入力 valarray の要素を演算し、入力 valarray の要素のタンジェントと等しい要素を持つ valarray を返します。|  
|[tanh](../Topic/tanh%20\(%3Cvalarray%3E\).md)|入力 valarray の要素を演算し、入力 valarray の要素のハイパーボリック タンジェントと等しい要素を持つ valarray を返します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\!\=](../Topic/operator!=%20\(%3Cvalarray%3E\).md)|サイズが等しい 2 つの valarray の対応する要素が等しくないか、あるいはある valarray のすべての要素が valarray の要素型の指定値と等しくないかをテストします。|  
|[operator%](../Topic/operator%25.md)|サイズが等しい 2 つの valarray の対応する要素を除算した剰余か、valarray の要素型の指定値で valarray を除算した剰余、または valarray で指定値を除算した剰余を取得します。|  
|[演算子 &](../Topic/operator&.md)|サイズが等しい 2 つの valarray の対応する要素間のビットごとの **AND**、または valarray と要素型の指定値との間のビットごとの **AND** を取得します。|  
|[operator&&](../Topic/operator&&.md)|サイズが等しい 2 つの valarray の対応する要素間の論理 **AND**、または valarray と valarray の要素型の指定値との間の論理 **AND** を取得します。|  
|[\> 演算子](../Topic/operator%3E%20\(%3Cvalarray%3E\).md)|ある valarray の要素がサイズが等しい valarray の要素より大きいか、またはある valarray のすべての要素が valarray の要素型の指定値より大きいか、もしくは指定値より小さいかをテストします。|  
|[\>\= 演算子](../Topic/operator%3E=%20\(%3Cvalarray%3E\).md)|ある valarray の要素がサイズが等しい valarray の要素以上であるか、またはある valarray のすべての要素が valarray の要素型の指定値以上であるか、もしくは指定値以下であるかをテストします。|  
|[演算子 \>\>](../Topic/operator%3E%3E%20\(%3Cvalarray%3E\).md)|valarray の各要素のビットを、指定された位置数だけ右にシフトさせるか、2 番目の valarray で指定された要素ごとの量だけ右にシフトさせます。|  
|[\< 演算子](../Topic/operator%3C%20\(%3Cvalarray%3E\).md)|ある valarray の要素がサイズが等しい valarray の要素未満であるか、またはある valarray のすべての要素が valarray の要素型の指定値より大きいか、もしくは指定値未満であるかをテストします。|  
|[\<\= 演算子](../Topic/operator%3C=%20\(%3Cvalarray%3E\).md)|ある valarray の要素がサイズが等しい valarray の要素以下であるか、またはある valarray のすべての要素が valarray の要素型の指定値以上であるか、もしくは指定値以下であるかをテストします。|  
|[演算子 \<\<](../Topic/operator%3C%3C%20\(%3Cvalarray%3E\).md)|valarray の各要素のビットを、指定された位置数だけ左にシフトさせるか、2 番目の valarray で指定された要素ごとの量だけ左にシフトさせます。|  
|[operator\*](../Topic/operator*%20\(%3Cvalarray%3E\).md)|サイズが等しい 2 つの valarray の対応する要素間の要素ごとの積、または valarray と valarray の要素型の指定値との間の積を取得します。|  
|[operator\+](../Topic/operator+%20\(%3Cvalarray%3E\).md)|サイズが等しい 2 つの valarray の対応する要素間の要素ごとの和、または valarray と valarray の要素型の指定値との間の和を取得します。|  
|[operator\-](../Topic/operator-%20\(%3Cvalarray%3E\)2.md)|サイズが等しい 2 つの valarray の対応する要素間の要素ごとの差、または valarray と valarray の要素型の指定値との間の差を取得します。|  
|[operator\/](../Topic/operator-%20\(%3Cvalarray%3E\)1.md)|サイズが等しい 2 つの valarray の対応する要素間の要素ごとの商、または valarray と valarray の要素型の指定値との間の商を取得します。|  
|[operator\=\=](../Topic/operator==%20\(%3Cvalarray%3E\).md)|サイズが等しい 2 つの valarray の対応する要素が等しいか、あるいはある valarray のすべての要素が valarray の要素型の指定値と等しいかをテストします。|  
|[operator^](../Topic/operator%5E.md)|サイズが等しい 2 つの valarray の対応する要素間のビットごとの排他的 `OR`、または valarray と要素型の指定値との間のビットごとの排他的 `OR` を取得します。|  
|[演算子 &#124;](../Topic/operator%7C.md)|サイズが等しい 2 つの valarray の対応する要素間のビットごとの `OR`、または valarray と要素型の指定値との間のビットごとの `OR` を取得します。|  
|[operator&#124;&#124;](../Topic/operator%7C%7C.md)|サイズが等しい 2 つの valarray の対応する要素間の論理 `OR`、または valarray と valarray の要素型の指定値との間の論理 `OR` を取得します。|  
  
### クラス  
  
|||  
|-|-|  
|[gslice クラス](../Topic/gslice%20Class.md)|valarray の多次元スライスを定義するのに使用する valarray のユーティリティ クラス。|  
|[gslice\_array クラス](../standard-library/gslice-array-class.md)|valarray の一般的なスライスで定義されるサブセット配列間の演算を実行して一般的なスライス オブジェクトをサポートする、内部の補助テンプレート クラス。|  
|[indirect\_array クラス](../standard-library/indirect-array-class.md)|親 valarray のインデックスのサブセットを指定することにより定義されるサブセット配列間の演算を実行して valarray のサブセットとして機能するオブジェクトをサポートする、内部の補助テンプレート クラス。|  
|[mask\_array クラス](../Topic/mask_array%20Class.md)|サブセット配列間の演算を提供することにより、ブール式で指定された親 valarray のサブセットとして機能するオブジェクトをサポートする、内部の補助テンプレート クラス。|  
|[slice クラス](../Topic/slice%20Class.md)|valarray のベクター的 1 次元サブセットを定義するのに使用する valarray のユーティリティ クラス。|  
|[slice\_array クラス](../standard-library/slice-array-class.md)|valarray のスライスで定義されるサブセット配列間の演算を提供することによりスライス オブジェクトをサポートする、内部の補助テンプレート クラス。|  
|[valarray クラス](../standard-library/valarray-class.md)|このテンプレート クラスは、配列として格納され、高速数値演算を実行するようにデザインされている、計算パフォーマンス用に最適化された **Type** 型の要素のシーケンスを制御するオブジェクトについて記述します。|  
  
### 特殊化  
  
|||  
|-|-|  
|[valarray\<bool\> クラス](../Topic/valarray%3Cbool%3E%20Class.md)|テンプレート クラス valarray\<**Type**\> を `bool` 型の要素に特化したバージョン。|  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)