---
title: "Invokehelper::invoke メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::Details::InvokeHelper::Invoke
dev_langs: C++
helpviewer_keywords: Invoke method
ms.assetid: 98618815-c30e-4699-b3dd-203c91b1bf3b
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a8707ac96c0417eddb015d7e802433bf071dda80
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="invokehelperinvoke-method"></a>InvokeHelper::Invoke メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHOD(  
   Invoke  
)();  
STDMETHOD(  
   Invoke  
)(typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
STDMETHOD(  
   Invoke  
)( typename Traits;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `arg1`  
 引数 1 です。  
  
 `arg2`  
 2 の引数。  
  
 `arg3`  
 引数 3 です。  
  
 `arg4`  
 4 の引数。  
  
 `arg5`  
 5 の引数。  
  
 `arg6`  
 6 の引数。  
  
 `arg7`  
 引数 7 です。  
  
 `arg8`  
 8 の引数。  
  
 `arg9`  
 9 の引数。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK、それ以外の場合、エラーを説明する HRESULT。  
  
## <a name="remarks"></a>コメント  
 指定した数の引数を含むシグネチャを持つイベント ハンドラーを呼び出します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>参照  
 [InvokeHelper 構造体](../windows/invokehelper-structure.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)