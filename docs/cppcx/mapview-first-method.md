---
title: "MapView::First メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::First"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView::First メソッド"
ms.assetid: 9d7c7328-4f55-4ea6-a375-9d4e73707b56
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# MapView::First メソッド
マップ ビュー内の最初の要素を指定する反復子を返します。  
  
## 構文  
  
```  
  
virtual Windows::Foundation::Collections::IIterator<  
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^   
First();  
```  
  
## 戻り値  
 マップ ビュー内の最初の要素を指定する反復子。  
  
## 解説  
 First\(\) によって返される反復子を保持する便利な方法は、[auto](~/cpp/auto-cpp.md) 型推論キーワードで宣言された変数に戻り値を代入することです。 たとえば、`auto x = myMapView->First();` のようにします。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::MapView クラス](../cppcx/platform-collections-mapview-class.md)