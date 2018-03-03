---
title: "FactoryCacheFlags 列挙型 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
dev_langs:
- C++
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 41b31ccede1cca717418c9f489ab7de67d313319
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="factorycacheflags-enumeration"></a>FactoryCacheFlags 列挙型
ファクトリ オブジェクトをキャッシュするかどうかを判断します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
enum FactoryCacheFlags;  
```  
  
## <a name="remarks"></a>コメント  
 既定では、ポリシーをキャッシュ ファクトリとして指定されて、 [ModuleType](../windows/moduletype-enumeration.md)テンプレート パラメーターを作成するとき、[モジュール](../windows/module-class.md)オブジェクト。 このポリシーを上書きするには、指定、`FactoryCacheFlags`ファクトリ オブジェクトを作成するときの値します。  
  
|||  
|-|-|  
|`FactoryCacheDefault`|キャッシュ ポリシー、`Module`オブジェクトを使用します。|  
|`FactoryCacheEnabled`|関係なくファクトリがキャッシュされるように、`ModuleType`の作成に使用するテンプレート パラメーター、`Module`オブジェクト。|  
|`FactoryCacheDisabled`|工場出荷時に関係なくキャッシュを無効にします`ModuleType`の作成に使用するテンプレート パラメーター、`Module`オブジェクト。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)