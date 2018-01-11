---
title: "Implements::cancastto メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Implements::CanCastTo
dev_langs: C++
helpviewer_keywords: CanCastTo method
ms.assetid: a8e85c7d-4dcd-446d-bebc-a97da46ce44a
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f1607b5fc290c398350b9e5c9d81eb50088b61c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="implementscancastto-method"></a>Implements::CanCastTo メソッド
指定されたインターフェイスへのポインターを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
__forceinline HRESULT CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `riid`  
 インターフェイス ID への参照  
  
 `ppv`  
 かどうかは成功すると、インターフェイスへのポインターで指定された`riid`です。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK、それ以外の場合、E_NOINTERFACE など、エラーを示す HRESULT。  
  
## <a name="remarks"></a>コメント  
 これは、QueryInterface 操作を実行する内部ヘルパー関数です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [Implements 構造体](../windows/implements-structure.md)