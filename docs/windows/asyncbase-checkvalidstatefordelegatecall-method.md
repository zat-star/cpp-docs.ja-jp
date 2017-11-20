---
title: "Asyncbase::checkvalidstatefordelegatecall メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall
dev_langs: C++
helpviewer_keywords: CheckValidStateForDelegateCall method
ms.assetid: d997ebe7-2378-4e74-a379-f0f85e6922f0
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0bc2ea8acd3811eb75a602f9dca8b7edff8fa786
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="asyncbasecheckvalidstatefordelegatecall-method"></a>AsyncBase::CheckValidStateForDelegateCall メソッド
現在の非同期状態でデリゲート プロパティを変更できるかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```  
inline HRESULT CheckValidStateForDelegateCall();  
```  
  
## <a name="return-value"></a>戻り値  
 デリゲート プロパティを変更できる場合は S_OK、それ以外の場合、E_ILLEGAL_METHOD_CALL です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [AsyncBase クラス](../windows/asyncbase-class.md)