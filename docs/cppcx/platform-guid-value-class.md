---
title: "Platform::Guid 値クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Guid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Guid 構造体"
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# Platform::Guid 値クラス
[GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931\(v=vs.85\).aspx) の種類を、Windows ランタイムの型システムで表します。  
  
## 構文  
  
```cpp  
public value struct Guid  
```  
  
## メンバー  
 GUID には、[Platform::Object クラス](../cppcx/platform-object-class.md)から派生した Equals\(\)、GetHashCode\(\)、ToString\(\)、GetTypeCode\(\) メソッド、および [Platform::Type クラス](../cppcx/platform-type-class.md). Guid には、次のメンバーもあります。  
  
|メンバー|説明|  
|----------|--------|  
|Guid|Guid 構造体の新しいインスタンスを初期化します。|  
|operator\=\=|等値演算子。|  
|operator\!\=|非等値演算子。|  
|演算子 \(\)|Guid を GUID に変換します。|  
  
## 解説  
 Windows の関数 [CoCreateGuid](http://msdn.microsoft.com/library/windows/desktop/ms688568\(v=vs.85\).aspx) を使用して新しい Platform::Guid を作成する例については、「[WinRT コンポーネント: GUID を作成する方法](http://blogs.msdn.com/b/eternalcoding/archive/2013/03/25/winrt-component-how-to-generate-a-guid.aspx)」を参照してください。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## 参照  
 [プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)