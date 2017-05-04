---
title: "Box::operator Box&lt;const T&gt;^ Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::operator Box<const T>^"
dev_langs: 
  - "C++"
ms.assetid: c43a2e8f-7e9d-4587-960f-1bab48923f82
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Box::operator Box&lt;const T&gt;^ Operator
`const` 値クラスの `T` または `enum` クラスの `T` から `Box<T>` へのボックス化変換を有効にします。  
  
## 構文  
  
```cpp  
operator Box<const T>^(const T valueType);  
```  
  
#### パラメーター  
 `T`  
 値クラス、値構造体、または列挙型。[既定の名前空間](../cppcx/default-namespace.md) に組み込み型を含めます。  
  
## 戻り値  
 ref クラスでボックス化された元の値を表す `Platform::Box<T>``^` インスタンス。  
  
## 必要条件  
 **ヘッダー:** vccorlib.h  
  
 **名前空間:** Platform  
  
## 参照  
 [Platform::Box クラス](../cppcx/platform-box-class.md)   
 [Platform::IBox インターフェイス](../cppcx/platform-ibox-interface.md)