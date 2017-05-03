---
title: "UnorderedMap::First メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::First"
ms.assetid: 915e771a-cec1-4905-8ecb-76501f63c143
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::First メソッド
順序なしのマップの最初の [Windows::Foundation::Collections::IKeyValuePair\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) 要素を指定する反復子を返します。  
  
## 構文  
  
```cpp  
  
virtual Windows::Foundation::Collections::IIterator<  
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();  
```  
  
## 戻り値  
 マップ内の最初の要素を指定する反復子。  
  
## 解説  
 First\(\) によって返される反復子を保持する便利な方法は、[auto](../Topic/auto%20\(C++\).md) 型推論キーワードで宣言された変数に戻り値を代入することです。 たとえば、`auto x = myUnorderedMap->First();` のようにします。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::UnorderedMap クラス](../cppcx/platform-collections-unorderedmap-class.md)   
 [コレクション](../cppcx/collections-c-cx.md)