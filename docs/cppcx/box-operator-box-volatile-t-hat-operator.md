---
title: "Box::operator Box&lt;volatile T&gt;^ Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::operator Box<volatile T>^"
dev_langs: 
  - "C++"
ms.assetid: 90fffbf6-3429-46d0-bfaf-d99b7f48de6f
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Box::operator Box&lt;volatile T&gt;^ Operator
`volatile` 値クラスの `T` または `enum` 型の `T` から `Box<T>` へのボックス化変換を有効にします。  
  
## 構文  
  
```cpp  
operator Box<volatile T>^(volatile T valueType);  
```  
  
#### パラメーター  
 `T`  
 列挙型、値クラス、または値構造体。[既定の名前空間](../cppcx/default-namespace.md) に組み込み型を含めます。  
  
## 戻り値  
 ref クラスでボックス化された元の値を表す `Platform::Box<T>``^` インスタンス。  
  
## 必要条件  
 **ヘッダー:** vccorlib.h  
  
 **名前空間:** Platform  
  
## 参照  
 [Platform::Box クラス](../cppcx/platform-box-class.md)   
 [Platform::IBox インターフェイス](../cppcx/platform-ibox-interface.md)   
 [ボックス化とボックス化解除](../cppcx/boxing-c-cx.md)