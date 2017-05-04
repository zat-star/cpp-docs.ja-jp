---
title: "Platform::Collections::VectorViewIterator クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator クラス"
ms.assetid: be3aa1ae-e6ba-4a06-8d6b-86d8128026f7
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# Platform::Collections::VectorViewIterator クラス
[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] `IVectorView` インターフェイスから派生したオブジェクト用の、標準テンプレート ライブラリ反復子を提供します。  
  
 `ViewVectorIterator` は、`VectorProxy<T>` 型の要素を格納するプロキシ反復子です。 ただし、プロキシ オブジェクトは、ユーザー コードにはほとんどは表示されません。 詳細については、「[Collections \(C\+\+\/CX\) \(コレクション \(C\+\+\/CX\)\)](../cppcx/collections-c-cx.md)」を参照してください。  
  
## 構文  
  
```  
template <  
   typename T  
>  
class VectorViewIterator;  
```  
  
#### パラメーター  
 `T`  
 VectorViewIterator テンプレート クラスの型名。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`difference_type`|ポインターの相違点 \(ptrdiff\_t\)。|  
|`iterator_category`|ランダム アクセス反復子 \(::std::random\_access\_iterator\_tag\) のカテゴリ。|  
|`pointer`|VectorViewIterator の実装に必要な内部型へのポインター。|  
|`reference`|VectorViewIterator の実装に必要な内部型への参照。|  
|`value_type`|`T` 型名。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[VectorViewIterator::VectorViewIterator コンストラクター](../cppcx/vectorviewiterator-vectorviewiterator-constructor.md)|VectorViewIterator クラスの新しいインスタンスを初期化します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[VectorViewIterator::operator\- 演算子](../cppcx/vectorviewiterator-operator-minus-operator.md)|現在の反復子から指定した数の要素を減算して新しい反復子を生成するか、現在の反復子から指定した反復子を減算して反復子間の要素数を生成します。|  
|[VectorViewIterator::operator\-\- 演算子](../cppcx/vectorviewiterator-operator-decrement-operator.md)|現在の VectorViewIterator をデクリメントします。|  
|[VectorViewIterator::operator\!\= 演算子](../cppcx/vectorviewiterator-operator-inequality-operator.md)|現在の VectorViewIterator が、指定された VectorViewIterator と等しくないかどうかを示します。|  
|[VectorViewIterator::operator\* 演算子](../cppcx/vectorviewiterator-operator-dereference-operator.md)|現在の VectorViewIterator により指定された要素への参照を取得します。|  
|[VectorViewIterator::operatorOperator](../cppcx/vectorviewiterator-operatoroperator.md)|現在の VectorViewIterator から指定数だけ転置された要素への参照を取得します。|  
|[VectorViewIterator::operator\+ 演算子](../cppcx/vectorviewiterator-operator-plus-operator.md)|指定された VectorViewIterator から指定された転置にある要素を参照する VectorViewIterator を返します。|  
|[VectorViewIterator::operator\+\+ 演算子](../cppcx/vectorviewiterator-operator-increment-operator.md)|現在の VectorViewIterator をインクリメントします。|  
|[VectorViewIterator::operator\+\= 演算子](../cppcx/vectorviewiterator-operator-plus-assign-operator.md)|指定された転置数だけ現在の VectorViewIterator をインクリメントします。|  
|[VectorViewIterator::operator\< 演算子](../cppcx/vectorviewiterator-operator-less-than-operator.md)|現在の VectorViewIterator が、指定された VectorViewIterator より小さいかどうかを示します。|  
|[VectorViewIterator::operator\<\= 演算子](../cppcx/vectorviewiterator-operator-less-than-or-equals-operator.md)|現在の VectorViewIterator が、指定された VectorViewIterator 以下であるかどうかを示します。|  
|[VectorViewIterator::operator\-\= 演算子](../cppcx/vectorviewiterator-operator-subtract-assign-operator.md)|現在の VectorViewIterator を、指定されたディスプレイスメントだけデクリメントします。|  
|[VectorViewIterator::operator\=\= 演算子](../cppcx/vectorviewiterator-operator-equality-operator.md)|現在の VectorViewIterator が、指定された VectorViewIterator と等しいかどうかを示します。|  
|[VectorViewIterator::operator\> 演算子](../cppcx/vectorviewiterator-operator-greater-than-operator.md)|現在の VectorViewIterator が、指定された VectorViewIterator より大きいかどうかを示します。|  
|[VectorViewIterator::operator\-\> 演算子](../cppcx/vectorviewiterator-operator-arrow-operator.md)|現在の VectorViewIterator により参照される要素のアドレスを取得します。|  
|[VectorViewIterator::operator\>\= 演算子](../cppcx/vectorviewiterator-operator-greater-than-or-equals-operator.md)|現在の VectorViewIterator が、指定された VectorViewIterator 以上であるかどうかを示します。|  
  
## 継承階層  
 `VectorViewIterator`  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [\(NOTINBUILD\) プラットフォーム名前空間](http://msdn.microsoft.com/ja-jp/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)