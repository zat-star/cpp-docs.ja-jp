---
title: "Platform::IBoxArray インターフェイス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IBoxArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::IBoxArray"
ms.assetid: 6cd82c9e-4230-4147-9edb-7a652875dbf1
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Platform::IBoxArray インターフェイス
`IBoxArray` はアプリケーション バイナリ インターフェイス \(ABI\) を越えて渡されるか、XAML コントロールなどの `Platform::Object^` 要素のコレクションに格納される値型の配列のラッパーです。  
  
## 構文  
  
```cpp  
template <typename T>  
interface class IBoxArray  
```  
  
#### パラメーター  
 `T`  
 各配列要素のボックス化された値の型。  
  
## 解説  
 `IBoxArray` は、[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] の [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] \(`Windows::Foundation::IReferenceArray`\) 名です。  
  
## メンバー  
 `IBoxArray` インターフェイスは `IValueType` インターフェイスを継承します。`IBoxArray` にも、次に示すメンバーがあります。  
  
|メソッド|説明|  
|----------|--------|  
|値|以前にこの `IBoxArray` インスタンスに格納されていたことがあり、ボックス化が解除されている配列を返します。|  
  
## 参照  
 [Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)