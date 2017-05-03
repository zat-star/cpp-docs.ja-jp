---
title: "Map::GetView メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::GetView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map::GetView メソッド"
ms.assetid: d432bb98-d354-4caa-8c2b-794406ac0b0b
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::GetView メソッド
現在のマップの読み取り専用ビュー、つまり、[Windows::Foundation::Collections::IMapView\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br226037.aspx) インターフェイスを実装する [Platform::Collections::MapView Class](../cppcx/platform-collections-mapview-class.md) を返します。  
  
## 構文  
  
```  
  
Windows::Foundation::Collections::IMapView<K, V>^   
   GetView();  
```  
  
## 戻り値  
 `MapView` オブジェクト。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::Map クラス](../cppcx/platform-collections-map-class.md)   
 [Platform::Collections::UnorderedMapClass](../cppcx/platform-collections-unorderedmap-class.md)   
 [コレクション \(C\+\+\/CX\)](../cppcx/collections-c-cx.md)