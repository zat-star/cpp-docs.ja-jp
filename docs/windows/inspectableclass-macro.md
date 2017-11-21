---
title: "InspectableClass マクロ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::InspectableClass
dev_langs: C++
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9f9cb2ac0ef10492d226fee9ef40d95c18b4f3ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="inspectableclass-macro"></a>InspectableClass マクロ
ランタイム クラス名と信頼レベルを設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
InspectableClass(  
   runtimeClassName,   
   trustLevel)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `runtimeClassName`  
 ランタイム クラス名のテキスト形式の完全な名前です。  
  
 `trustLevel`  
 1 つ、 [TrustLevel](http://msdn.microsoft.com/library/br224625.aspx)列挙値。  
  
## <a name="remarks"></a>コメント  
 `InspectableClass`マクロは Windows ランタイム型でのみ使用できます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [RuntimeClass クラス](../windows/runtimeclass-class.md)