---
title: "RuntimeClassType 列挙型 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClassType
dev_langs: C++
helpviewer_keywords: RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 26016e8c95807af76484504c491ca1e6e08f8f96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType 列挙型
型を指定[RuntimeClass](../windows/runtimeclass-class.md)サポートされているインスタンス。  
  
## <a name="syntax"></a>構文  
  
```  
enum RuntimeClassType;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`ClassicCom`|クラシック COM ランタイム クラスです。|  
|`Delegate`|等価**ClassicCom**です。|  
|`InhibitFtmBase`|無効に`FtmBase`中にサポート`__WRL_CONFIGURATION_LEGACY__`が定義されていません。|  
|`InhibitWeakReference`|弱い参照のサポートを無効にします。|  
|`WinRt`|Windows ランタイム クラスです。|  
|`WinRtClassicComMix`|`WinRt` と `ClassicCom` の組み合わせです。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)