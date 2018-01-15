---
title: "Comptr::comptr コンス トラクター |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::ComPtr
dev_langs: C++
helpviewer_keywords: ComPtr, constructor
ms.assetid: eaf70907-beac-458f-a503-2e5e27b0c196
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f8f6234bf2dff0dab801c982a585dc30e338bb7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="comptrcomptr-constructor"></a>ComPtr::ComPtr コンストラクター
ComPtr クラスの新しいインスタンスを初期化します。 オーバーロードは、既定、コピー、移動、および変換の各コンストラクターを提供します。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW ComPtr();  
WRL_NOTHROW ComPtr(  
   decltype(__nullptr)  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr(  
   const ComPtr& other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   const ComPtr<U> &other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr &&other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr<U>&& other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `U`  
 `other` パラメーターの型。  
  
 `other`  
 `U` 型のオブジェクト。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="remarks"></a>コメント  
 最初のコンス トラクターは、どの暗黙的空のオブジェクトを作成する既定のコンス トラクターです。 2 番目のコンス トラクターを指定[_ _nullptr](../windows/nullptr-cpp-component-extensions.md)、空のオブジェクトを明示的に作成します。  
  
 3 番目のコンス トラクターは、ポインターで指定されたオブジェクトからオブジェクトを作成します。  
  
 4 番目と 5 番目のコンス トラクターは、コピー コンス トラクターです。 5 番目のコンス トラクターは、現在の型に変換可能である場合、オブジェクトをコピーします。  
  
 6 番目と 7 番目のコンス トラクターは、移動コンス トラクターです。 7 番目のコンス トラクターは、現在の型に変換可能である場合、オブジェクトを移動します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [ComPtr クラス](../windows/comptr-class.md)