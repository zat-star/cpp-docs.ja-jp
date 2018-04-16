---
title: "AsyncStatusInternal 列挙型 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
dev_langs:
- C++
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bd277fecb0bc63d5ee823af98df8aa298b285964
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal 列挙型
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
enum AsyncStatusInternal;  
```  
  
## <a name="remarks"></a>コメント  
 非同期操作の状態の内部列挙値の間のマッピングを指定し、 **Windows::Foundation::AsyncStatus**列挙します。  
  
## <a name="members"></a>メンバー  
 `_Created`  
 等価:: Windows::Foundation::AsyncStatus:: を作成  
  
 `_Started`  
 等価:: Windows::Foundation::AsyncStatus:: 開始  
  
 `_Completed`  
 等価:: Windows::Foundation::AsyncStatus:: 完了  
  
 `_Cancelled`  
 等価:: Windows::Foundation::AsyncStatus:: 取り消されました  
  
 `_Error`  
 等価:: Windows::Foundation::AsyncStatus::Error  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** async.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)