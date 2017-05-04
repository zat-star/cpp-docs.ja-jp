---
title: "String::Length メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::Length"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::Length"
ms.assetid: 92376897-1bf2-4b7a-9298-d2d3f05d8d6b
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::Length メソッド
現在の String オブジェクト内の文字数を取得します。  
  
## 構文  
  
```cpp  
  
unsigned int Length()  
```  
  
## 戻り値  
 現在の String オブジェクト内の文字数。  
  
## 解説  
 文字がない場合の String の長さはゼロです。 次の文字列は長さが 5 になります。  
  
```  
  
String^ str = "Hello";  
int len = str->Length(); //len = 5  
```  
  
 [String::Data メソッド](../cppcx/string-data-method.md) によって返される文字配列には、末尾に NULL と '\\0' のいずれかの文字が 1 つ追加されます。 この文字は、長さが 2 バイトです。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** vccorlib.h  
  
## 参照  
 [Platform::String クラス](../cppcx/platform-string-class.md)