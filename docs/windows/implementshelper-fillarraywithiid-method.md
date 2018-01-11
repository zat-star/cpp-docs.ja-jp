---
title: "Implementshelper::fillarraywithiid メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid
dev_langs: C++
helpviewer_keywords: FillArrayWithIid method
ms.assetid: f60035ee-b7d6-4a08-966d-f88c646944c3
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eeb2254933dc0f9f5e4b99ba4e010dbe3afbb7cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="implementshelperfillarraywithiid-method"></a>ImplementsHelper::FillArrayWithIid メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
void FillArrayWithIid(  
   _Inout_ unsigned long *index,   
   _Inout_ IID* iids) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `index`  
 この操作の開始の配列要素を示す 0 から始まるインデックス。 この操作が完了したら、 `index` 1 ずつインクリメントされます。  
  
 `iids`  
 型の Iid の配列。  
  
## <a name="remarks"></a>コメント  
 指定した配列の要素に現在の 0 番目のテンプレート パラメーターで指定されたインターフェイス ID を挿入します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>参照  
 [ImplementsHelper 構造体](../windows/implementshelper-structure.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)