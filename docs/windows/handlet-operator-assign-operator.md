---
title: "Handlet::operator = 演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
dev_langs: C++
helpviewer_keywords: operator= operator
ms.assetid: 9e42dcca-30fa-4e8b-8954-802fd64a5595
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 68afd6b2a0a1c17cd032d6cea84aefde8c368204
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="handletoperator-operator"></a>HandleT::operator= 演算子
指定した HandleT オブジェクトの値を現在 HandleT オブジェクトに移動します。  
  
## <a name="syntax"></a>構文  
  
```  
HandleT& operator=(  
   _Inout_ HandleT&& h  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `h`  
 ハンドルを右辺値の参照。  
  
## <a name="return-value"></a>戻り値  
 現在の HandleT オブジェクトへの参照。  
  
## <a name="remarks"></a>コメント  
 この操作には、パラメーターで指定された HandleT オブジェクトが無効になります。`h`です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>参照  
 [HandleT クラス](../windows/handlet-class.md)