---
title: "AsyncResultType 列挙型 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncResultType
dev_langs: C++
helpviewer_keywords: AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b654a4f27ca78cda680a7ceb69f0c6e2ea0db9a4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType 列挙型
GetResults() メソッドによって返される結果の型を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
enum AsyncResultType;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`MultipleResults`|開始状態の間で、Close() を呼び出す前に、段階的に記載されている複数の結果のセット。|  
|`SingleResult`|1 つの結果、完全なイベントの発生後に表示されます。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)