---
title: "MapView::Split メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::Split"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView::Split メソッド"
ms.assetid: b863e223-2282-4d1a-b995-77a690120542
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# MapView::Split メソッド
現在の MapView を 2 つの MapView オブジェクトに分割します。 このメソッドは操作不可です。  
  
## 構文  
  
```  
void Split(  
   Windows::Foundation::Collections::IMapView<  
                         K,  
                         V>^ * firstPartition,  
   Windows::Foundation::Collections::IMapView<  
                         K,  
                         V>^ * secondPartition  
);  
```  
  
#### パラメーター  
 `firstPartition`  
 元の MapView オブジェクトの最初の部分。  
  
 `secondPartition`  
 元の MapView オブジェクトの 2 番目の部分。  
  
## 解説  
 このメソッドは操作可能ではありません。これは何も実行しません。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::MapView クラス](../cppcx/platform-collections-mapview-class.md)