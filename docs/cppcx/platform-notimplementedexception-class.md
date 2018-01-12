---
title: "Platform::notimplementedexception クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Platform::NotImplementedException
- VCCORLIB/Platform::NotImplementedException::NotImplementedException
dev_langs: C++
helpviewer_keywords: Platform::NotImplementedException
ms.assetid: 6da26cc2-dde8-4aea-aa85-67aac55cf97b
caps.latest.revision: "3"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b1c4053f31da7324ebe418e8603f788a52cbed63
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="platformnotimplementedexception-class"></a>Platform::NotImplementedException クラス
インターフェイス メンバーが派生型で実装されていない場合にスローされます。  
  
## <a name="syntax"></a>構文  
  
```cpp  
public ref class NotImplementedException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
### <a name="remarks"></a>コメント  
 詳細については、 [COMException](../cppcx/platform-comexception-class.md) クラスを参照してください。  
  
### <a name="requirements"></a>必要条件  
 **クライアントがサポートされる最小:** Windows 8  
  
 **サポートされているサーバーの最小値:** Windows Server 2012  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## <a name="see-also"></a>参照  
 [Platform::COMException クラス](../cppcx/platform-comexception-class.md)