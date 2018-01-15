---
title: "Creatormap::activationid データ メンバー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Details::CreatorMap::activationId
dev_langs: C++
helpviewer_keywords: activationId data member
ms.assetid: 77518b76-6e6a-4b48-8e2e-a4c7c67769e0
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 912b18ff3e1be04913cb9345e4ac5bde25d2e039
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="creatormapactivationid-data-member"></a>CreatorMap::activationId データ メンバー
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
union {   
   const IID* clsid;  
   const wchar_t* (*getRuntimeName)();  
} activationId;  
```  
  
## <a name="parameters"></a>パラメーター  
 `clsid`  
 インターフェイス ID。  
  
 `getRuntimeName`  
 Windows ランタイム オブジェクトの名前を取得する関数。  
  
## <a name="remarks"></a>コメント  
 クラシック COM クラス ID または Windows ランタイム名前によって識別されるオブジェクト ID を表します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>参照  
 [CreatorMap 構造体](../windows/creatormap-structure.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)