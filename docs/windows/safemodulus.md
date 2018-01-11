---
title: "SafeModulus |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: SafeModulus
dev_langs: C++
helpviewer_keywords: SafeModulus function
ms.assetid: ae5c81eb-5dcf-45a5-aa76-465fdfe68654
caps.latest.revision: "6"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 383382de2720ac7a72403bd3578e235af7bdbe05
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="safemodulus"></a>SafeModulus
2 つの数値に対して剰余演算を実行します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename T, typename U>  
inline bool SafeModulus (  
   const T t,  
   const U u,  
   T& result  
) throw ();  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `t`  
 除数。 T 型でなければなりません  
  
 [入力] `u`  
 被除数。 U 型です。 これでなければなりません  
  
 [出力] `result`  
 パラメーターで`SafeModulus`結果を格納します。  
  
## <a name="return-value"></a>戻り値  
 `true`エラーが発生しない場合です。`false`場合は、エラーが発生します。  
  
## <a name="remarks"></a>コメント  
 このメソッドの一部である[SafeInt ライブラリ](../windows/safeint-library.md)のインスタンスを作成することがなく 1 つの剰余演算のものでは、 [SafeInt クラス](../windows/safeint-class.md)です。  
  
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