---
title: "Comptr::operator = 演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::operator=
dev_langs: C++
helpviewer_keywords: operator= operator
ms.assetid: 1a0c2752-f7d8-4819-9443-07b88b69ef02
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 30f04bdfe7b508bf83e34992fefdcb10c58b4655
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="comptroperator-operator"></a>ComPtr::operator= 演算子
値を現在の ComPtr に割り当てます。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW ComPtr& operator=(  
   decltype(__nullptr)  
);  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ T *other  
);  
template <  
   typename U  
>  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr &other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr<U>& other  
);  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr &&other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr<U>&& other  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `U`  
 クラスです。  
  
 `other`  
 もう 1 つの ComPtr、または型へのポインター、参照、または右辺値参照。  
  
## <a name="return-value"></a>戻り値  
 現在の ComPtr への参照。  
  
## <a name="remarks"></a>コメント  
 この演算子の最初のバージョンでは、現在の ComPtr に空の値を割り当てます。  
  
 2 番目のバージョンでは、割り当てのインターフェイス ポインターが現在の ComPtr インターフェイス ポインターと同じでない場合、2 番目のインターフェイス ポインターが現在の ComPtr に割り当てられます。  
  
 3 番目のバージョンでは、割り当てのインターフェイス ポインターが現在の ComPtr に割り当てられます。  
  
 4 番目のバージョンでは、割り当ての値のインターフェイス ポインターが現在の ComPtr インターフェイス ポインターと同じでない場合、2 番目のインターフェイス ポインターが現在の ComPtr に割り当てられます。  
  
 5 番目のバージョンがコピー演算子です。ComPtr への参照は、現在の ComPtr に割り当てられます。  
  
 6 番目のバージョンがコピー演算子を使用する移動セマンティクスです。ComPtr キャストし、現在の ComPtr に代入して、任意の型が静的な場合に右辺値参照。  
  
 7 番目のバージョンがコピー演算子を使用する移動セマンティクスです。型の ComPtr への右辺値参照`U`静的キャストし、現在の ComPtr に割り当てられています。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [ComPtr クラス](../windows/comptr-class.md)