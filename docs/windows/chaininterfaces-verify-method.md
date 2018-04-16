---
title: "Chaininterfaces::verify メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::Verify
dev_langs:
- C++
helpviewer_keywords:
- Verify method
ms.assetid: c591e130-8686-4130-ba69-1aaedc250038
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d34d117091fd8807dfefda074e510910bf059560
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="chaininterfacesverify-method"></a>ChainInterfaces::Verify メソッド
テンプレート パラメーターによって、各インターフェイスが定義されていることを確認`I0`を通じて`I9`IUnknown や、IInspectable から継承`I0`から継承`I1`を通じて`I9`です。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW __forceinline static void Verify();  
```  
  
## <a name="remarks"></a>コメント  
 検証操作が失敗した場合、`static_assert`エラーを示すエラー メッセージを出力します。  
  
## <a name="remarks"></a>コメント  
 テンプレート パラメーター`I0`と`I1`が必要ですが、およびパラメーター`I2`を通じて`I9`は省略可能です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [ChainInterfaces 構造体](../windows/chaininterfaces-structure.md)