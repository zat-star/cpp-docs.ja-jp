---
title: "SafeAdd |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: SafeAdd
dev_langs: C++
helpviewer_keywords: SafeAdd function
ms.assetid: 3f82b91d-59fe-4ee1-873b-d056182fa8be
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 394a79554acad936a180a8bde0a04b5e6d10069f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="safeadd"></a>SafeAdd
オーバーフローを防止する方法の 2 つの数値を加算します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename T, typename U>  
inline bool SafeAdd (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `t`  
 追加する最初の数。 T 型でなければなりません  
  
 [入力] `u`  
 追加する 2 番目の数値。 U 型です。 これでなければなりません  
  
 [出力] `result`  
 パラメーターで`SafeAdd`結果を格納します。  
  
## <a name="return-value"></a>戻り値  
 `true`エラーが発生しない場合です。`false`場合は、エラーが発生します。  
  
## <a name="remarks"></a>コメント  
 このメソッドの一部である[SafeInt ライブラリ](../windows/safeint-library.md)のインスタンスを作成せず、1 つの追加操作のものでは、 [SafeInt クラス](../windows/safeint-class.md)です。  
  
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
 [SafeSubtract](../windows/safesubtract.md)