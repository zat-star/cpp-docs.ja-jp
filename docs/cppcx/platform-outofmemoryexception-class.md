---
title: "Platform::outofmemoryexception クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Platform::OutOfMemoryException
- VCCORLIB/Platform::OutOfMemoryException::OutOfMemoryException
dev_langs: C++
helpviewer_keywords: Platform::OutOfMemoryException
ms.assetid: 49c19f6b-f66c-4448-b861-91dcbf32de2c
caps.latest.revision: "3"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 84368cd26fd0e3e9bd73b5863a2575d82a75b113
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="platformoutofmemoryexception-class"></a>Platform::OutOfMemoryException クラス
メモリが不足して操作を完了できないときにスローされます。  
  
## <a name="syntax"></a>構文  
  
```cpp  
public ref class OutOfMemoryException : COMException,    IException,    IPrintable,    IEquatable  
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