---
title: "Platform::TypeCode 列挙型 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::TypeCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::TypeCode 列挙型"
ms.assetid: 93c1305f-eb16-4bec-aead-f88d9518b4cf
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 3
---
# Platform::TypeCode 列挙型
組み込み型を表す数値カテゴリを指定します。  
  
## 構文  
  
```cpp  
enum class TypeCode {};  
```  
  
## メンバー  
  
|型コード|説明|  
|----------|--------|  
|ブール型|Platform::Boolean 型。|  
|Char16|default::char16 型。|  
|DateTime|DateTime 型です。|  
|Decimal \(10 進数型\)|数値型。|  
|倍精度浮動小数点型|default::float64 型。|  
|Empty|Void|  
|Int16|default::int16 型。|  
|Int32|default::int32 型。|  
|Int64|default::int64 型。|  
|Int8|default::int8 型。|  
|オブジェクト|Platform::Object 型。|  
|Single|default::float32 型。|  
|String|Platform::String 型。|  
|UInt16|default::uint16 型。|  
|UInt32|default::uint32 型。|  
|UInt64|default::uint64 型。|  
|UInt8|default::uint8 型。|  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd