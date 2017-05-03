---
title: "WriteOnlyArray::end メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::WriteOnlyArray::end"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WriteOnlyArray::end メソッド"
ms.assetid: 045045fe-f210-400b-b688-7abb95fc702a
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WriteOnlyArray::end メソッド
配列内の最後の要素の 1 つ後ろを指すポインターを返します。  
  
## 構文  
  
```cpp  
T* end() const;  
```  
  
## 戻り値  
 配列内の最後の要素の 1 つ後ろを指すポインター反復子。  
  
## 解説  
 この反復子は、配列要素に対して `std::sort` などの操作を実行するために STL アルゴリズムと共に使用できます。  
  
## 必要条件  
 **ヘッダー:** vccorlib.h  
  
 **名前空間:** Platform  
  
## 参照  
 [Platform::WriteOnlyArray クラス](../cppcx/platform-writeonlyarray-class.md)   
 [Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)