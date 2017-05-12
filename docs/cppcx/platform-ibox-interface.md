---
title: "Platform::IBox インターフェイス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IBox"
dev_langs: 
  - "C++"
ms.assetid: 774df45d-f8a7-45a3-ae24-eecc3c681040
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Platform::IBox インターフェイス
[Platform::IBox](../cppcx/platform-ibox-interface.md) のインターフェイスは `Windows::Foundation::IReference` のインターフェイスの C\+\+ の名前です。  
  
## 構文  
  
```cpp  
template <typename T>  
interface class IBox  
```  
  
#### パラメーター  
 `T`  
 ボックス化された値の型。  
  
## 解説  
 `IBox<T>` インターフェイスは、「[値クラスと構造体 \(C\+\+\/CX\)](../cppcx/value-classes-and-structs-c-cx.md)」で説明されているように、主に内部的に使用され、null 許容値型を表します。 インターフェイスは、`Object^` 型のパラメーターを受け取る C\+\+ のメソッドに渡される値の型をボックス化するためにも使用されます。 入力パラメーターは `IBox<SomeValueType>` として明示的に宣言できます。 例については、「[ボックス化とボックス化解除](../cppcx/boxing-c-cx.md)」を参照してください。  
  
## 必要条件  
  
## メンバー  
 `Platform::IBox` インターフェイスは [Platform::IValueType](../cppcx/platform-ivaluetype-interface.md) インターフェイスから継承されます。`IBox` には、次に示すメンバーがあります。  
  
 **プロパティ**  
  
|メソッド|説明|  
|----------|--------|  
|値|以前にこの `IBox` インスタンスに格納されていたことがあり、ボックス化が解除されている値を返します。|  
  
## 参照  
 [プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)