---
title: "Guid::operator() 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Guid::operator()"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Guid::operator()"
  - "プラットフォーム、Guid::operator()"
ms.assetid: 5df51e6a-11c0-414c-8613-06b45a952828
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Guid::operator() 演算子
暗黙的に [GUID 構造体](http://msdn.microsoft.com/library/windows/desktop/aa373931\(v=vs.85\).aspx) GUID を Platform::Guid に変換します。  
  
## 構文  
  
```cpp  
Platform::Guid operator()  
```  
  
## 戻り値  
 GUID 構造体。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## 参照  
 [Platform::Guid 値クラス](../cppcx/platform-guid-value-class.md)