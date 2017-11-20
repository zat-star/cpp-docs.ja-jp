---
title: "InterfaceList 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::InterfaceList
dev_langs: C++
helpviewer_keywords: InterfaceList structure
ms.assetid: 6ec3228d-eb3e-4b7e-aef1-7dcf17bdf61a
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a9c7c14dc24bf76444b62adb0870b85fac449e67
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="interfacelist-structure"></a>InterfaceList 構造体
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   typename T,  
   typename U  
>  
struct InterfaceList;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 インターフェイスの名前です。再帰的なリストの最初のインターフェイスです。  
  
 `U`  
 インターフェイスの名前です。再帰的なリスト内の残りインターフェイスです。  
  
## <a name="remarks"></a>コメント  
 インターフェイスの再帰的なリストを作成するために使用します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`FirstT`|テンプレート パラメーターのシノニム`T`です。|  
|`RestT`|テンプレート パラメーターのシノニム`U`です。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `InterfaceList`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)