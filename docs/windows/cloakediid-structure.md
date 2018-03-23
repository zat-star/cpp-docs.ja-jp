---
title: CloakedIid 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
dev_langs:
- C++
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 075694e83f4c0e2004ccc9a86b03a0f7b7ea7f78
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2018
---
# <a name="cloakediid-structure"></a>CloakedIid 構造体
IID リスト内で指定されたインターフェイスにアクセスできないことを、RuntimeClass、Implements、および ChainInterfaces テンプレートに示します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename T>  
struct CloakedIid : T;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 インターフェイスは表示されません (クロークされています)。  
  
## <a name="remarks"></a>コメント  
 CloakedIid の使用方法の例を次に示します:`struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `T`  
  
 `CloakedIid`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)