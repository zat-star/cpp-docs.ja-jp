---
title: "Vector::First メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::First"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::First メソッド"
ms.assetid: ca6b7b55-dd49-4346-bfa4-d8010b228d44
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::First メソッド
Vector 内の最初の要素を指す反復子を返します。  
  
## 構文  
  
```  
  
virtual Windows::Foundation::Collections::IIterator <T>^   
   First();  
```  
  
## 戻り値  
 Vector 内の最初の要素を指す反復子。  
  
## 解説  
 First\(\) によって返される反復子を保持する便利な方法は、[auto](../Topic/auto%20\(C++\).md) 型推論キーワードで宣言された変数に戻り値を代入することです。 たとえば、`auto x = myVector->First();` のようにします。 この反復子は、コレクションの長さを認識しています。  
  
 STL 関数に渡す 1 組の反復子が必要な場合は、free 関数 [Windows::Foundation::Collections::begin](../cppcx/begin-function.md) および [Windows::Foundation::Collections::end](../cppcx/end-function.md) を使用します。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::Vector クラス](../cppcx/platform-collections-vector-class.md)   
 [コレクション](../cppcx/collections-c-cx.md)