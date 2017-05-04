---
title: "Type::FullName プロパティ | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Type::get_FullName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Type::get_FullName プロパティ"
ms.assetid: b5a12d8f-4404-4659-b4af-e7d23a1e44b7
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Type::FullName プロパティ
現在の型の "Namespace.Type" 形式の完全修飾名を取得します。  
  
## 構文  
  
```cpp  
String^ FullName();  
```  
  
## 戻り値  
 型の名前。  
  
## 使用例  
  
```  
  
//  namespace is TestApp MainPage::MainPage() { InitializeComponent(); Type^ t = this->GetType(); auto s = t->FullName; // returns “TestApp.MainPage” auto s2 = t->ToString(); //also returns “TestApp.MainPage” }  
```  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## 参照  
 [Platform::ValueType クラス](../cppcx/platform-valuetype-class.md)