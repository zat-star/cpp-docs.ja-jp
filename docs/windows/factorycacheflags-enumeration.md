---
title: "FactoryCacheFlags 列挙型 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::FactoryCacheFlags"
dev_langs: 
  - "C++"
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# FactoryCacheFlags 列挙型
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ファクトリ オブジェクトをキャッシュするかどうかを決定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
enum FactoryCacheFlags;  
```  
  
## <a name="remarks"></a>コメント  
 として既定では、工場出荷時のキャッシュ ポリシーが指定されている、 [ModuleType](../Topic/ModuleType%20Enumeration.md) テンプレート パラメーターを作成するとき、 [モジュール](../windows/module-class.md) オブジェクトです。 このポリシーを上書きするには、指定、 `FactoryCacheFlags` ファクトリ オブジェクトを作成するときの値します。  
  
|||  
|-|-|  
|`FactoryCacheDefault`|キャッシュ ポリシー、 `Module` オブジェクトを使用します。|  
|`FactoryCacheEnabled`|関係なくファクトリがキャッシュできるように、 `ModuleType` の作成に使用するテンプレート パラメーター、 `Module` オブジェクトです。|  
|`FactoryCacheDisabled`|工場出荷時のキャッシュを無効にします `ModuleType` の作成に使用するテンプレート パラメーター、 `Module` オブジェクトです。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::wrl 名前空間](../windows/microsoft-wrl-namespace.md)