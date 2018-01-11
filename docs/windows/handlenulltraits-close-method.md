---
title: "Handlenulltraits::close メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close
dev_langs: C++
helpviewer_keywords: Close method
ms.assetid: 6fb2fa0d-df20-45dc-856f-f78497f8bdf9
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dbe3f8ebe8c63eda026da92aec037037830a763d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="handlenulltraitsclose-method"></a>HANDLENullTraits::Close メソッド
指定したハンドルを閉じます。  
  
## <a name="syntax"></a>構文  
  
```  
inline static bool Close(  
   _In_ Type h  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `h`  
 閉じるハンドルです。  
  
## <a name="return-value"></a>戻り値  
 **true**場合処理`h`正常です。 それ以外の場合、閉じられた**false**です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>参照  
 [HANDLENullTraits 構造体](../windows/handlenulltraits-structure.md)