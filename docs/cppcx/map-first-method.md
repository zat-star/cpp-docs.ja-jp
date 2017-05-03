---
title: "Map::First メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::First"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map::First メソッド"
ms.assetid: bb1a4458-ecc3-43b0-b808-1693f853ad82
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::First メソッド
マップ内の最初の要素を指定する反復子、またはマップが空の場合は `nullptr` を返します。  
  
## 構文  
  
```  
  
virtual Windows::Foundation::Collections::IIterator<  
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();  
```  
  
## 戻り値  
 マップ内の最初の要素を指定する反復子。  
  
## 解説  
 First\(\) によって返される反復子を保持する便利な方法は、[auto](../Topic/auto%20\(C++\).md) 型推論キーワードで宣言された変数に戻り値を代入することです。 たとえば、`auto x = myMap->First();` のようにします。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::Map クラス](../cppcx/platform-collections-map-class.md)   
 [コレクション \(C\+\+\/CX\)](../cppcx/collections-c-cx.md)