---
title: "FactoryCache 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache
dev_langs:
- C++
helpviewer_keywords:
- FactoryCache structure
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0fc48c9a3651e8c5a6609886862c2f73c5707638
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="factorycache-structure"></a>FactoryCache 構造体
Windows ランタイム C++ テンプレート ライブラリのインフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
struct FactoryCache;  
```  
  
## <a name="remarks"></a>コメント  
 クラス ファクトリと、登録されている wrt を識別する値または COM クラスのオブジェクトの場所が含まれています。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[FactoryCache::cookie データ メンバー](../windows/factorycache-cookie-data-member.md)|オブジェクトを識別、登録されている Windows ランタイムまたは COM クラス、およびオブジェクトの登録を解除する際に使用する値が含まれています。|  
|[FactoryCache::factory データ メンバー](../windows/factorycache-factory-data-member.md)|Windows ランタイムまたは COM クラス ファクトリを指します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `FactoryCache`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)