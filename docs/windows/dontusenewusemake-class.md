---
title: "DontUseNewUseMake クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::DontUseNewUseMake
dev_langs: C++
helpviewer_keywords: DontUseNewUseMake class
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 62f8abc151758ac9253698390cbab3e2ba62a4c5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake クラス
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
class DontUseNewUseMake;  
```  
  
## <a name="remarks"></a>コメント  
 演算子を使用できないように`new`RuntimeClass にします。 したがって、使用する必要があります、[関数](../windows/make-function.md)代わりにします。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[DontUseNewUseMake::operator new 演算子](../windows/dontusenewusemake-operator-new-operator.md)|演算子をオーバー ロード`new`と RuntimeClass で使用されていることを防ぎます。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `DontUseNewUseMake`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [Make 関数](../windows/make-function.md)