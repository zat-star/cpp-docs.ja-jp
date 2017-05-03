---
title: "Platform::Collections::VectorIterator クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator クラス"
ms.assetid: d531cb42-27e0-48a6-bf5e-c265891a18ff
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Platform::Collections::VectorIterator クラス
[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] IVector インターフェイスから派生したオブジェクト用の、標準テンプレート ライブラリ反復子を提供します。  
  
 VectorIterator は、型 VectorProxy\<T\> の要素を格納するプロキシ反復子です。 ただし、プロキシ オブジェクトは、ユーザー コードにはほとんどは表示されません。 詳細については、「[Collections \(C\+\+\/CX\) \(コレクション \(C\+\+\/CX\)\)](../cppcx/collections-c-cx.md)」を参照してください。  
  
## 構文  
  
```  
template <  
   typename T  
>  
class VectorIterator;  
```  
  
#### パラメーター  
 `T`  
 VectorIterator テンプレート クラスの型名。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`difference_type`|ポインターの相違点 \(ptrdiff\_t\)。|  
|`iterator_category`|ランダム アクセス反復子 \(::std::random\_access\_iterator\_tag\) のカテゴリ。|  
|`pointer`|VectorIterator の実装に必要な内部型 Platform::Collections::Details::VectorProxy\<T\> へのポインター。|  
|`reference`|VectorIterator の実装に必要な内部型 Platform::Collections::Details::VectorProxy\<T\> への参照。|  
|`value_type`|`T` 型名。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[VectorIterator::VectorIterator コンストラクター](../cppcx/vectoriterator-vectoriterator-constructor.md)|VectorIterator クラスの新しいインスタンスを初期化します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[VectorIterator::operator\- 演算子](../cppcx/vectoriterator-operator-minus-operator.md)|現在の反復子から指定した数の要素を減算して新しい反復子を生成するか、現在の反復子から指定した反復子を減算して反復子間の要素数を生成します。|  
|[VectorIterator::operator\-\- 演算子](../cppcx/vectoriterator-operator-decrement-operator.md)|現在の VectorIterator をデクリメントします。|  
|[VectorIterator::operator\!\= 演算子](../cppcx/vectoriterator-operator-inequality-operator.md)|現在の VectorIterator が、指定された VectorIterator と等しくないかどうかを示します。|  
|[VectorIterator::operator\* 演算子](../cppcx/vectoriterator-operator-dereference-operator.md)|現在の VectorIterator により指定された要素への参照を取得します。|  
|[VectorIterator::operatorOperator](../cppcx/vectoriterator-operatoroperator.md)|現在の VectorIterator から指定された転置にある要素への参照を取得します。|  
|[\(DELETE\) VectorIterator::operator\+ 演算子](http://msdn.microsoft.com/ja-jp/b0b1af2c-e2a8-4876-99dc-7351bfc46ce4)|指定された VectorIterator から指定された転置にある要素を参照する VectorIterator を返します。|  
|[VectorIterator::operator\+\+ 演算子](../cppcx/vectoriterator-operator-increment-operator.md)|現在の VectorIterator をインクリメントします。|  
|[VectorIterator::operator\+\= 演算子](../cppcx/vectoriterator-operator-plus-assign-operator.md)|指定されたディスプレイスメントだけ現在の VectorIterator をインクリメントします。|  
|[VectorIterator::operator\< 演算子](../cppcx/vectoriterator-operator-less-than-operator.md)|現在の VectorIterator が、指定された VectorIterator より小さいかどうかを示します。|  
|[VectorIterator::operator\<\= 演算子](../cppcx/vectoriterator-operator-less-than-or-equals-operator.md)|現在の VectorIterator が、指定された VectorIterator 以下かどうかを示します。|  
|[VectorIterator::operator\-\= 演算子](../cppcx/vectoriterator-operator-subtract-assign-operator.md)|指定されたディスプレイスメントだけ現在の VectorIterator をデクリメントします。|  
|[VectorIterator::operator\=\= 演算子](../cppcx/vectoriterator-operator-equality-operator.md)|現在の VectorIterator が、指定された VectorIterator と等しいかどうかを示します。|  
|[VectorIterator::operator\> 演算子](../cppcx/vectoriterator-operator-greater-than-operator.md)|現在の VectorIterator が、指定された VectorIterator より大きいかどうかを示します。|  
|[VectorIterator::operator\-\> 演算子](../cppcx/vectoriterator-operator-arrow-operator.md)|現在の VectorIterator により参照される要素のアドレスを取得します。|  
|[VectorIterator::operator\>\= 演算子](../cppcx/vectoriterator-operator-greater-than-or-equal-operator.md)|現在の VectorIterator が、指定された VectorIterator 以上であるかどうかを示します。|  
  
## 継承階層  
 `VectorIterator`  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [\(NOTINBUILD\) Platform 名前空間](http://msdn.microsoft.com/ja-jp/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)