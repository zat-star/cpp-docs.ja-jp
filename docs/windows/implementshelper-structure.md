---
title: "ImplementsHelper 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::ImplementsHelper
dev_langs: C++
helpviewer_keywords: ImplementsHelper structure
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1a51de59278e476be1e99b60ef1b0ab8a6e3f3cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="implementshelper-structure"></a>ImplementsHelper 構造体
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   typename RuntimeClassFlagsT,  
   typename ILst,  
   bool IsDelegateToClass  
>  
friend struct Details::ImplementsHelper;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `RuntimeClassFlagsT`  
 1 つ以上を指定するフラグのフィールド[RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙子。  
  
 `ILst`  
 インターフェイスの Id の一覧。  
  
 `IsDelegateToClass`  
 指定`true`実装の現在のインスタンスで最初のインターフェイス ID の基本クラスである場合`ILst`、それ以外の`false`します。  
  
## <a name="remarks"></a>コメント  
 により、実装、 [Implements](../windows/implements-structure.md)構造体。  
  
 このテンプレートは、インターフェイスのリストを走査し、QueryInterface を有効にするために必要な情報と、基底クラスとしては、それらを追加します。  
  
## <a name="members"></a>メンバー  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ImplementsHelper`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>参照  
 [参照 (Windows ランタイム ライブラリ)](http://msdn.microsoft.com/en-us/00000000-0000-0000-0000-000000000000)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)