---
title: "Object::ToString メソッド (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object::ToString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "プラットフォーム、Object::ToString"
ms.assetid: 229dbf1c-cb43-4ed2-a1c5-a1f36b22a7ea
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Object::ToString メソッド (C++/CX)
現在のオブジェクトを表す文字列を返します。  
  
## 構文  
  
```cpp  
public:  
virtual String^ ToString()  
```  
  
## 戻り値  
 現在のオブジェクトを表す文字列。 ref クラスまたは構造体内でカスタム文字列メッセージを表示するために、このメソッドをオーバーライドすることもできます:  
  
```cpp  
public ref class Tree sealed { public: Tree(){} virtual Platform::String^ ToString()override { return "I’m a Tree"; }; };  
```  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **ヘッダー:** vccorlib.h  
  
## 参照  
 [Platform::Object クラス](../cppcx/platform-object-class.md)