---
title: "Vector::GetAt メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::GetAt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::GetAt メソッド"
ms.assetid: 3766b399-cef2-4006-9a87-50f717390cac
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::GetAt メソッド
指定されたインデックスで識別される現在のベクターの要素を取得します。  
  
## 構文  
  
```  
  
virtual T GetAt(  
   unsigned int index  
);  
```  
  
#### パラメーター  
 `index`  
 ベクター オブジェクト内の特定の要素を指定する、0 から始まる符号なし整数。  
  
## 戻り値  
 `index` パラメーターで指定された要素。 要素の型は、*T* 型名によって定義されます。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::Vector クラス](../cppcx/platform-collections-vector-class.md)