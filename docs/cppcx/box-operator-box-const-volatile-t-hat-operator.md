---
title: "Box::operator Box&lt;const volatile T&gt;^ Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::operator Box<const volatile T>^"
dev_langs: 
  - "C++"
ms.assetid: 3c91cf0f-1e90-4daf-8468-a7d8aedb6784
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Box::operator Box&lt;const volatile T&gt;^ Operator
`const volatile` 値クラスの `T` または `enum` 型の `T` から `Box<T>` へのボックス化変換を有効にします。  
  
## 構文  
  
```cpp  
operator Box<const volatile T>^(const volatile T valueType);  
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