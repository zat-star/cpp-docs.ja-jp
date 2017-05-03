---
title: "UnorderedMap::GetView メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::GetView"
ms.assetid: 41a12802-3f42-461c-a6fc-a35fc34517f2
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::GetView メソッド
現在のマップの読み取り専用ビュー、つまり、[Windows::Foundation::Collections::IMapView::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx) インターフェイスを実装する [Platform::Collections::UnorderedMapView クラス](../cppcx/platform-collections-unorderedmapview-class.md) を返します。  
  
## 構文  
  
```scr  
  
Windows::Foundation::Collections::IMapView<K, V>^   
   GetView();  
```  
  
## 戻り値  
 `UnorderedMapView` オブジェクト。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [コレクション](../cppcx/collections-c-cx.md)   
 [Platform::Collections::UnorderedMap クラス](../cppcx/platform-collections-unorderedmap-class.md)   
 [Platform::Collections::UnorderedMapView クラス](../cppcx/platform-collections-unorderedmapview-class.md)