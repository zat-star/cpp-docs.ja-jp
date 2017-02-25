---
title: "数値 (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "<cliext/numeric>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/numeric> ヘッダー [STL/CLR]"
  - "<numeric> ヘッダー [STL/CLR]"
  - "数値関数 [STL/CLR]"
ms.assetid: 1dc4d9a3-e734-459c-9678-5d9be0ef4c79
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# 数値 (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

数値処理に使用されるアルゴリズムを実行するコンテナーのテンプレート関数を定義します。  
  
## 構文  
  
```  
#include <cliext/numeric>  
```  
  
## 関数  
  
|関数|説明|  
|--------|--------|  
|[accumulate](../dotnet/accumulate-stl-clr.md)|初期値を含めて、指定した範囲内のすべての要素の合計を逐次的に対する部分を計算して計算、または指定二項演算の使用から取得した合計以外の連続する部分的な結果の結果を計算します。|  
|[adjacent\_difference](../dotnet/adjacent-difference-stl-clr.md)|入力範囲内の各要素と過去の連続する相違点を計算し、割り当て先範囲に結果を出力するか、相違点操作が他方の置換一般化されたプロシージャ、指定二項演算の結果を計算します。|  
|[inner\_product](../dotnet/inner-product-stl-clr.md)|2 種類の span 要素の積の合計を計算し、指定された初期値に追加したり、合計や製品の二項演算が他の指定二項演算が別の一般的な手順の結果を計算します。|  
|[partial\_sum](../dotnet/partial-sum-stl-clr.md)|入力計算の一連の合計は最初の要素の `i`th 要素を受け取り、移動先の範囲または計算の `i`th 要素のこのような合計合計操作の結果が別の指定二項演算が別の一般的な手順の結果またがります。|  
  
## 必要条件  
 **ヘッダー:** の \<cliext\/桁数\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [STL\/CLR ライブラリ](../dotnet/stl-clr-library-reference.md)