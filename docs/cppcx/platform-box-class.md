---
title: "Platform::Box クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box"
dev_langs: 
  - "C++"
ms.assetid: b3d7ea37-e98a-4fbc-80b0-ad35e50250c6
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Platform::Box クラス
`Windows::Foundation::DateTime` などの値型または `int` などのスカラー型を `Platform::Object` 型に格納できるようにします。 通常は、`Box` を明示的に使用する必要はありません。これは、値型を `Object^` にキャストすると、ボックス化が暗黙的に発生するためです。  
  
## 構文  
  
```cpp  
ref class Box abstract;  
```  
  
## 解説  
  
## 必要条件  
 **ヘッダー:** vccorlib.h  
  
 **名前空間:** Platform  
  
## 参照  
 [プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)   
 [ボックス化とボックス化解除](../cppcx/boxing-c-cx.md)