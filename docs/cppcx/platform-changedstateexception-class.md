---
title: "Platform::changedstateexception クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Platform::ChangedStateException
- VCCORLIB/Platform::ChangedStateException::ChangedStateException
dev_langs: C++
helpviewer_keywords: Platform::ChangedStateException
ms.assetid: f894beac-9e80-4fac-ac25-89f1dbc0a6a4
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e874cb1ca3db5741d2974499c53e23816e204186
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="platformchangedstateexception-class"></a>Platform::ChangedStateException クラス
オブジェクトの内部状態が変化したときにスローされ、メソッドの結果を無効にします。  
  
## <a name="syntax"></a>構文  
  
```cpp  
public ref class ChangedStateException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
### <a name="remarks"></a>コメント  
 この例外がスローされる 1 つの例は、コレクション反復子またはコレクション ビューのメソッドが、親コレクションの変更後に呼び出された場合です。この結果、メソッドの結果は無効になります。  
  
 詳細については、 [COMException](../cppcx/platform-comexception-class.md) クラスを参照してください。  
  
### <a name="requirements"></a>必要条件  
 **クライアントがサポートされる最小:** Windows 8  
  
 **サポートされているサーバーの最小値:** Windows Server 2012  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## <a name="see-also"></a>参照  
 [Platform::COMException クラス](../cppcx/platform-comexception-class.md)