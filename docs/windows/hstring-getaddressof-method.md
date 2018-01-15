---
title: "Hstring::getaddressof メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HString::GetAddressOf
dev_langs: C++
ms.assetid: 6050decf-5f99-49f0-9497-1c8192c485ae
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cc4c15570b65b62b22f0dd9a7f66f8c244e2bf22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="hstringgetaddressof-method"></a>HString::GetAddressOf メソッド
基になる HSTRING ハンドルへのポインターを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
HSTRING* GetAddressOf() throw()  
```  
  
## <a name="return-value"></a>戻り値  
 基になる HSTRING ハンドルへのポインター。  
  
## <a name="remarks"></a>コメント  
 この操作の後に、文字列、基になる HSTRING ハンドルの値は破棄されます。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>参照  
 [HString クラス](../windows/hstring-class.md)