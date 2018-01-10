---
title: "SafeMultiply |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: SafeMultiply
dev_langs: C++
helpviewer_keywords: SafeMultiply function
ms.assetid: 81d988a5-fac7-4930-8c37-c24fa8e2c853
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 37ea091136521fc83fc63a8fb752e0f4f72cb49f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="safemultiply"></a>SafeMultiply
オーバーフローを防止する方法で同時に 2 つの数値を乗算します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename T, typename U>  
inline bool SafeMultiply (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `t`  
 乗算対象の最初の数。 T 型でなければなりません  
  
 [入力] `u`  
 乗算対象の 2 番目の数。 U 型です。 これでなければなりません  
  
 [出力] `result`  
 パラメーターで`SafeMultiply`結果を格納します。  
  
## <a name="return-value"></a>戻り値  
 `true`エラーが発生しない場合です。`false`場合は、エラーが発生します。  
  
## <a name="remarks"></a>コメント  
 このメソッドの一部である[SafeInt ライブラリ](../windows/safeint-library.md)のインスタンスを作成することがなく 1 つの乗算演算のものでは、 [SafeInt クラス](../windows/safeint-class.md)です。  
  
> [!NOTE]
>  このメソッドは、単一の数値演算を保護する必要がありますにのみ使用する必要があります。 使用する必要があります複数の操作がある場合、`SafeInt`個々 のスタンドアロン関数の呼び出しではなくクラスです。  
  
 テンプレート型 T および U の詳細については、次を参照してください。 [SafeInt 関数](../windows/safeint-functions.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** safeint.h  
  
 **Namespace:** Microsoft::Utilities  
  
## <a name="see-also"></a>参照  
 [SafeInt 関数](../windows/safeint-functions.md)   
 [SafeInt ライブラリ](../windows/safeint-library.md)   
 [SafeInt クラス](../windows/safeint-class.md)   
 [SafeDivide](../windows/safedivide.md)