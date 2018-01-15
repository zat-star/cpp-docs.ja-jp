---
title: "AsWeak 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::AsWeak
dev_langs: C++
helpviewer_keywords: AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2bc994c502a806fcca0ead9a5c73aa6f8b5dd02e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="asweak-function"></a>AsWeak 関数
指定されたインスタンスへの弱い参照を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
template<  
   typename T  
>  
HRESULT AsWeak(  
   _In_ T* p,  
   _Out_ WeakRef* pWeak  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 パラメーターの型へのポインター`p`です。  
  
 `p`  
 型のインスタンス。  
  
 `pWeak`  
 この操作の完了時、パラメーターへの弱い参照へのポインター`p`です。  
  
## <a name="return-value"></a>戻り値  
 この操作が成功した場合は S_OK、それ以外の場合、エラーのエラーの原因を示す hresult 値。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)