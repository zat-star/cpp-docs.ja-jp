---
title: "Weakreference::resolve メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::WeakReference::Resolve
dev_langs: C++
helpviewer_keywords: Resolve method
ms.assetid: fc65a4b7-48a0-4d64-a793-37f566fdd8e7
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9dc2eef072e64d38b96afd045bae6a9b23d59d94
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="weakreferenceresolve-method"></a>WeakReference::Resolve メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
  
STDMETHOD(Resolve)  
   (REFIID riid,   
   _Deref_out_opt_ IInspectable **ppvObject  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `riid`  
 インターフェイス ID。  
  
 `ppvObject`  
 この操作の完了時、強力な参照カウントが 0 以外の場合は、現在の強い参照のコピー。  
  
## <a name="return-value"></a>戻り値  
  
-   この操作が成功して、強力な参照カウントがゼロの場合は S_OK、します。 `ppvObject` パラメーターを `nullptr` に設定します。  
  
-   この操作が成功して、強力な参照カウントが 0 でない場合は S_OK です。 `ppvObject`パラメーターは、強い参照に設定します。  
  
-   それ以外の場合、原因を示す HRESULT この操作に失敗しました。  
  
## <a name="remarks"></a>コメント  
 強力な参照カウントが 0 以外の場合は、現在の強い参照値に指定されたポインターを設定します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [WeakReference Class1](../windows/weakreference-class1.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)