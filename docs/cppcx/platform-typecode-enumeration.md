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
ms.openlocfilehash: 0c217824496f0cf4e69c8fba89fd614a8049a8c0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
|オブジェクト|Platform::Object 型。|  
|Single|default::float32 型。|  
|String|Platform::String 型。|  
|UInt16|default::uint16 型。|  
|UInt32|default::uint32 型。|  
|UInt64|default::uint64 型。|  
|UInt8|default::uint8 型。|  
  
### <a name="requirements"></a>要件  
 **クライアントがサポートされる最小:** Windows 8  
  
 **サポートされているサーバーの最小値:** Windows Server 2012  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd