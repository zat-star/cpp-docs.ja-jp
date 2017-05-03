---
title: "Box::Value プロパティ | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::Value"
dev_langs: 
  - "C++"
ms.assetid: f456b105-6c14-4737-8c27-ad47d1eabd32
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Box::Value プロパティ
`Box` オブジェクトにカプセル化された値を返します。  
  
## 構文  
  
```cpp  
virtual property T Value{  
   T get();  
}  
```  
  
## 戻り値  
 値がボックス化される前と同じ型のボックス化された値を返します。  
  
## 必要条件  
 **ヘッダー:** vccorlib.h  
  
 **名前空間:** Platform  
  
## 参照  
 [Platform::Box クラス](../cppcx/platform-box-class.md)   
 [ボックス化とボックス化解除](../cppcx/boxing-c-cx.md)