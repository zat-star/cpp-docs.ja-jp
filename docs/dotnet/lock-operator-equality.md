---
title: "lock::operator = = |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- lock::operator==
- msclr.lock.operator==
- msclr::lock::operator==
- lock.operator==
dev_langs:
- C++
helpviewer_keywords:
- lock::operator==
ms.assetid: 3dcf1e5a-53fc-495d-9df5-d7849a41c36c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 60922b0074a1ce10a4c6f61d73d3c20f3381f508
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="lockoperator"></a>lock::operator==
等値演算子。  
  
## <a name="syntax"></a>構文  
  
```  
template<class T> bool operator==(  
   T t  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `t`  
 等しいかどうかを比較するオブジェクト。  
  
## <a name="return-value"></a>戻り値  
 返します`true`場合`t`はロックのオブジェクトと同じ`false`それ以外の場合。  
  
## <a name="example"></a>例  
  
```  
// msl_lock_op_eq.cpp  
// compile with: /clr  
#include <msclr/lock.h>  
  
using namespace System;  
using namespace System::Threading;  
using namespace msclr;  
  
int main () {  
   Object^ o1 = gcnew Object;  
   lock l1(o1);  
   if (l1 == o1) {  
      Console::WriteLine("Equal!");  
   }  
}  
```  
  
```Output  
Equal!  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー ファイル** \<msclr\lock.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>参照  
 [lock のメンバー](../dotnet/lock-members.md)   
 [lock::operator!=](../dotnet/lock-operator-inequality.md)