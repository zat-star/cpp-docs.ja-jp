---
title: "Platform::ReCreateException メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::ReCreateException"
dev_langs: 
  - "C++"
ms.assetid: fa73d1ab-86e4-4d26-a7d9-81938c1c7e77
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::ReCreateException メソッド
これは内部でのみ使用されるメソッドであり、ユーザー コードには使用されません。 代わりに、[Exception::CreateException メソッド](../cppcx/exception-createexception-method.md)を使用してください。  
  
## 構文  
  
```vb  
static Exception^ ReCreateException(int hr)  
```  
  
#### パラメーター  
  
## プロパティ値\/戻り値  
 指定された HRESULT に基づいて新しい Platform::Exception^ を返します。  
  
## 同等の .NET Framework 関数  
  
## 必要条件