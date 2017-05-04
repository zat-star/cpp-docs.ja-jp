---
title: "ArrayReference::operator() 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::ArrayReference::operatorArray^"
dev_langs: 
  - "C++"
ms.assetid: 48726344-82bb-4c1d-b246-ed74b895f99b
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# ArrayReference::operator() 演算子
現在の [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) オブジェクトを変換して [Platform::Array](../cppcx/platform-array-class.md) クラスに戻します。  
  
## 構文  
  
```cpp  
  
Array<__TArg>^ operator ();  
  
```  
  
## 戻り値  
 `Array<__TArg>^` 型のオブジェクトへのハンドル。  
  
## 解説  
 [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) と [Platform::Array](../cppcx/platform-array-class.md) は、ref クラスではなく、標準 C\+\+ クラス テンプレートです。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **ヘッダー:** vccorlib.h  
  
## 参照  
 [Platform::ArrayReference クラス](../cppcx/platform-arrayreference-class.md)