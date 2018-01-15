---
title: "Asyncbase::currentstatus メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::CurrentStatus
dev_langs: C++
helpviewer_keywords: CurrentStatus method
ms.assetid: 26ee4c4a-6525-4a5f-b49c-3ca40c365eb6
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c72e66a179e47e890cbe90da7a3e54afa41ce942
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbasecurrentstatus-method"></a>AsyncBase::CurrentStatus メソッド
現在の非同期操作の状態を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
inline void CurrentStatus(  
   Details::AsyncStatusInternal *status  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `status`  
 この操作が現在の状態を格納する場所です。  
  
## <a name="remarks"></a>コメント  
 この操作は、スレッド セーフです。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [AsyncBase クラス](../windows/asyncbase-class.md)   
 [AsyncStatusInternal 列挙型](../windows/asyncstatusinternal-enumeration.md)