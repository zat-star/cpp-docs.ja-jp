---
title: "WeakReference::operator= | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/WeakReference::operator="
ms.assetid: 20b034d1-8f4f-46ae-81f0-73b76599f86b
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WeakReference::operator=
WeakReference に値を代入します。  
  
## 構文  
  
```cpp  
WeakReference& operator=(decltype(__nullptr));  
  
WeakReference& operator=(const WeakReference& __otherArg);  
  
WeakReference& operator=(WeakReference&& __otherArg);  
  
WeakReference& operator=(const volatile ::Platform::Object^ const __otherArg);  
  
```  
  
## 解説  
 上記のリストの最後のオーバーロードを使用すると、WeakReference 変数に ref クラスを代入できます。 この場合、ref クラスは [Platform::Object](../cppcx/platform-object-class.md)^ にダウンキャストされます。 後から元の型を復元するには、それを [WeakReference::Resolve\<T\>](../cppcx/weakreference-resolve-method-platform-namespace.md) メンバー関数の型パラメーターの引数として指定します。  
  
## 必要条件  
 Windows 8.0 以降  
  
## 参照  
 [Platform::WeakReference クラス](../cppcx/platform-weakreference-class.md)