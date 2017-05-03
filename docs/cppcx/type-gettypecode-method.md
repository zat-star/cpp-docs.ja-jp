---
title: "Type::GetTypeCode メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Type::GetTypeCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Type::GetTypeCode メソッド"
ms.assetid: 20c30432-91a3-400e-b9d6-eba265daaefc
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Type::GetTypeCode メソッド
組み込み型の数値型カテゴリを取得します。  
  
## 構文  
  
```cpp  
Platform::TypeCode GetTypeCode();  
```  
  
## 戻り値  
 Platform::TypeCode 列挙値のいずれか。  
  
## 解説  
 `typeid` プロパティが GetTypeCode\(\) メンバー メソッドに相当します。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## 参照  
 [Platform::ValueType クラス](../cppcx/platform-valuetype-class.md)