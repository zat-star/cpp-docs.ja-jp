---
title: "Handlet::attach メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleT::Attach
dev_langs: C++
helpviewer_keywords: Attach method
ms.assetid: a8783a18-bbf6-456c-98a3-e2048a10d79f
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 572221b7232e25984d78ec903f8d13b9e08ba06b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="handletattach-method"></a>HandleT::Attach メソッド
指定したハンドルを現在の HandleT オブジェクトに関連付けます。  
  
## <a name="syntax"></a>構文  
  
```  
void Attach(  
   typename HandleTraits::Type h  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `h`  
 ハンドル。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HandleT クラス](../windows/handlet-class.md)