---
title: "Asyncbase::put_id メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::put_Id
dev_langs: C++
helpviewer_keywords: put_Id method
ms.assetid: aebad85f-4774-42de-b625-a9cf5f65cb4e
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 60135d69f6f3f8b73256fd65d89651351bd100e5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbaseputid-method"></a>AsyncBase::put_Id メソッド
非同期操作のハンドルを設定します。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHOD(  
   put_Id  
)(const unsigned int id);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `id`  
 0 以外のハンドル。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK、それ以外の場合、E_INVALIDARG または E_ILLEGAL_METHOD_CALL します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [AsyncBase クラス](../windows/asyncbase-class.md)