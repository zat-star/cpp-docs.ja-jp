---
title: "Platform::Collections::BackInsertIterator クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::BackInsertIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BackInsertIterator クラス"
ms.assetid: aecee1ff-100d-4129-b84b-1966f0923dbf
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::Collections::BackInsertIterator クラス
要素を上書きするのではなく、シーケンシャル コレクションの末尾に要素を挿入する反復子を表します。  
  
## 構文  
  
```  
template <  
   typename T  
>  
class BackInsertIterator : public ::std::iterator< ::std::output_iterator_tag, void, void, void, void>;  
```  
  
#### パラメーター  
 `T`  
 現在のコレクション内の項目の型。  
  
## 解説  
 BackInsertIterator クラスは、[back\_insert\_iterator クラス](../standard-library/back-insert-iterator-class.md) が要求する規則を実装します。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[BackInsertIterator::BackInsertIterator コンストラクター](../cppcx/backinsertiterator-backinsertiterator-constructor.md)|BackInsertIterator クラスの新しいインスタンスを初期化します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[BackInsertIterator::operator\* 演算子](../cppcx/backinsertiterator-operator-dereference-operator.md)|現在の BackInsertIterator への参照を取得します。|  
|[BackInsertIterator::operator\+\+ 演算子](../cppcx/backinsertiterator-operator-increment-operator.md)|現在の BackInsertIterator への参照を返します。 反復子は変更されません。|  
|[BackInsertIterator::operator\= 演算子](../cppcx/backinsertiterator-operator-assign-operator.md)|指定されたオブジェクトを、現在のシーケンシャル コレクションの末尾に追加します。|  
  
## 継承階層  
 `BackInsertIterator`  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [\(NOTINBUILD\) Platform 名前空間](http://msdn.microsoft.com/ja-jp/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)