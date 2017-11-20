---
title: "CloakedIid 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::CloakedIid
dev_langs: C++
helpviewer_keywords: CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5a10752fecadaf3a7f044e3c563931ae3cdbe1b4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="cloakediid-structure"></a>CloakedIid 構造体
IID リスト内で指定されたインターフェイスにアクセスできないことを、RuntimeClass、Implements、および ChainInterfaces テンプレートに示します。  
  
## <a name="syntax"></a>構文  
  
```  
template<  
   typename T  
>  
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