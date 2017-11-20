---
title: "SafeDivide |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: SafeDivide
dev_langs: C++
helpviewer_keywords: SafeDivide function
ms.assetid: b5b27484-ad6e-46b1-ba9f-1c7120dd103b
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 59998367d71658a0561a4bda8d71bf6c4f61f313
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="safedivide"></a>SafeDivide
ゼロ除算を防止する方法の 2 つの数値を除算します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename T, typename U>  
inline bool SafeDivide (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `t`  
 除数。 T 型でなければなりません  
  
 [入力] `u`  
 被除数。 U 型です。 これでなければなりません  
  
 [出力] `result`  
 パラメーターで`SafeDivide`結果を格納します。  
  
## <a name="return-value"></a>戻り値  
 `true`エラーが発生しない場合です。`false`場合は、エラーが発生します。  
  
## <a name="remarks"></a>コメント  
 このメソッドの一部である[SafeInt ライブラリ](../windows/safeint-library.md)のインスタンスを作成せず、1 つの分割操作のものでは、 [SafeInt クラス](../windows/safeint-class.md)です。  
  
> [!NOTE]
>  このメソッドは、単一の数値演算を保護する必要がありますにのみ使用する必要があります。 使用する必要があります複数の操作がある場合、`SafeInt`個々 のスタンドアロン関数の呼び出しではなくクラスです。  
  
 テンプレート型 T および U の詳細については、次を参照してください。 [SafeInt 関数](../windows/safeint-functions.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** safeint.h  
  
 **Namespace:** Microsoft::Utilities  
  
## <a name="see-also"></a>関連項目  
 [SafeInt 関数](../windows/safeint-functions.md)   
 [SafeInt ライブラリ](../windows/safeint-library.md)   
 [SafeInt クラス](../windows/safeint-class.md)   
 [SafeModulus](../windows/safemodulus.md)   
 [SafeMultiply](../windows/safemultiply.md)