---
title: "BoolStruct 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: internal/Microsoft::WRL::Details::BoolStruct
dev_langs: C++
helpviewer_keywords: BoolStruct structure
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7daa7527c8eea2cfca3b8933b9c3e1f042883e2d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="boolstruct-structure"></a>BoolStruct 構造体
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
struct BoolStruct;  
```  
  
## <a name="remarks"></a>コメント  
 BoolStruct 構造体は、ComPtr がインターフェイスのオブジェクトの有効期間を管理するかどうかを定義します。 BoolStruct が内部で使用される、 [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)演算子。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[BoolStruct::Member データ メンバー](../windows/boolstruct-member-data-member.md)|指定する、 [ComPtr](../windows/comptr-class.md)またはインターフェイスのオブジェクトの有効期間の管理ではありません。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `BoolStruct`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL::Details Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtr::operator Microsoft::WRL::Details::BoolType 演算子](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)