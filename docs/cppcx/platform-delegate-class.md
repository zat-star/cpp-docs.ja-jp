---
title: "Platform::delegate クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Delegate
dev_langs:
- C++
helpviewer_keywords:
- Platform::Delegate Class
ms.assetid: 82b21271-768f-4193-9ca2-be68ddfd546e
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 603d159572ac998f1ad04ed3558b1f2d88457708
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="platformdelegate-class"></a>Platform::Delegate クラス
関数オブジェクトを表します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
public delegate void delegate_name();  
```  
  
### <a name="members"></a>メンバー  
 Delegate クラスには、 [Platform::Object Class](../cppcx/platform-object-class.md)から派生した Equals()、GetHashCode()、ToString() メソッドがあります。  
  
### <a name="remarks"></a>コメント  
 デリゲートを作成するには [delegate](../windows/delegate-cpp-component-extensions.md) キーワードを使用します。Platform::Delegate を明示的に使用しないでください。 詳細については、「[デリゲート](../cppcx/delegates-c-cx.md)」を参照してください。 作成し、デリゲートの利用方法の例は、次を参照してください。 [C++ での Windows ランタイム コンポーネントの作成](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)です。  
  
### <a name="requirements"></a>必要条件  
 **クライアントがサポートされる最小:** Windows 8  
  
 **サポートされているサーバーの最小値:** Windows Server 2012  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## <a name="see-also"></a>参照  
 [Platform 名前空間](../cppcx/platform-namespace-c-cx.md)