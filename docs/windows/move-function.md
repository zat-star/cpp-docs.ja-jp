---
title: "Move 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: internal/Microsoft::WRL::Details::Move
dev_langs: C++
helpviewer_keywords: Move function
ms.assetid: c9525426-97e8-4d8c-9877-b689d8a0dc67
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a894ca11eb6b5703c116d3fa3a36a45bb46d4ed3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="move-function"></a>Move 関数
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
template<  
   class T  
>  
inline typename RemoveReference<T>::Type&& Move(  
   _Inout_ T&& arg  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 引数の型。  
  
 `arg`  
 移動に渡す引数。  
  
## <a name="return-value"></a>戻り値  
 パラメーター`arg`参照または右辺値参照の特徴の後に存在する場合、削除されました。  
  
## <a name="remarks"></a>コメント  
 指定された引数を 1 つの場所から移動します。  
  
 詳細については、次を参照してください。、**移動セマンティクス**のセクション[右辺値参照宣言子: & &](../cpp/rvalue-reference-declarator-amp-amp.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)