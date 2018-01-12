---
title: "Platform::typecode 列挙 |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: VCCORLIB/Platform::TypeCode
dev_langs: C++
helpviewer_keywords: Platform::TypeCode Enumeration
ms.assetid: 93c1305f-eb16-4bec-aead-f88d9518b4cf
caps.latest.revision: "3"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 353649f63a8e5522329459b1c9f740450818a3af
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="platformtypecode-enumeration"></a>Platform::TypeCode 列挙型
組み込み型を表す数値カテゴリを指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
enum class TypeCode {};  
```  
  
### <a name="members"></a>メンバー  
  
|型コード|説明|  
|---------------|-----------------|  
|ブール型|Platform::Boolean 型。|  
|Char16|default::char16 型。|  
|DateTime|DateTime 型です。|  
|Decimal (10 進数型)|数値型。|  
|倍精度浮動小数点型|default::float64 型。|  
|Empty|Void|  
|Int16|default::int16 型。|  
|Int32|default::int32 型。|  
|Int64|default::int64 型。|  
|Int8|default::int8 型。|  
|Object|Platform::Object 型。|  
|Single|default::float32 型。|  
|String|Platform::String 型。|  
|UInt16|default::uint16 型。|  
|UInt32|default::uint32 型。|  
|UInt64|default::uint64 型。|  
|UInt8|default::uint8 型。|  
  
### <a name="requirements"></a>必要条件  
 **クライアントがサポートされる最小:** Windows 8  
  
 **サポートされているサーバーの最小値:** Windows Server 2012  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd