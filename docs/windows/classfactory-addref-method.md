---
title: "Classfactory::addref メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::ClassFactory::AddRef
dev_langs: C++
helpviewer_keywords: AddRef method
ms.assetid: 5b091785-dea4-42b6-a502-0db5fc7a5a2e
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 111bcef652660f8119d9c8dccd9345545506fe1a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="classfactoryaddref-method"></a>ClassFactory::AddRef メソッド
ClassFactory、現在の参照カウントをインクリメントします。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHOD_(  
   ULONG,  
   AddRef  
)();  
```  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [ClassFactory クラス](../windows/classfactory-class.md)