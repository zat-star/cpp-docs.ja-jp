---
title: "Comptrref::comptrref コンス トラクター |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRef::ComPtrRef
dev_langs: C++
helpviewer_keywords: ComPtrRef, constructor
ms.assetid: ce2d2533-fef6-4b2d-b088-6f3db01df5a5
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1a23af63156650aa215ca65610a3c8f54bf39461
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="comptrrefcomptrref-constructor"></a>ComPtrRef::ComPtrRef コンストラクター
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
ComPtrRef(  
   _In_opt_ T* ptr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ptr`  
 ComPtrRef オブジェクトを別の基になる値です。  
  
## <a name="remarks"></a>コメント  
 別の ComPtrRef オブジェクトを指定したポインターから ComPtrRef クラスの新しいインスタンスを初期化します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [ComPtrRef クラス](../windows/comptrref-class.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)