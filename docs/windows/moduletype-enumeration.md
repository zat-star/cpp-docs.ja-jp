---
title: "ModuleType 列挙型 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
dev_langs:
- C++
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dd68d911a3734510bfb35db4b3ee0c4b8e46a4a0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="moduletype-enumeration"></a>ModuleType 列挙型
モジュールがインプロセス サーバーまたはアウトプロセス サーバーをサポートするかどうかを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
enum ModuleType;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`InProc`|・ インプロセス サーバーです。|  
|`OutOfProc`|アウト プロセス サーバーの場合。|  
|`DisableCaching`|モジュール上のキャッシュ メカニズムを無効にします。|  
|`InProcDisableCaching`|組み合わせ`InProc`と`DisableCaching`です。|  
|`OutOfProcDisableCaching`|組み合わせ`OutOfProc`と`DisableCaching`です。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)