---
title: "SafeGreaterThan |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: SafeGreaterThan
dev_langs: C++
helpviewer_keywords: SafeGreaterThan function
ms.assetid: 32cecac9-ba88-43eb-a7a4-30e390456739
caps.latest.revision: "6"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 82f3d666e6e0c5a09f0968547b732b3735d23d2e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="safegreaterthan"></a>SafeGreaterThan
2 つの数値を比較します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename T, typename U>  
inline bool SafeGreaterThan (  
   const T t,  
   const U u  
) throw ();  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `t`  
 比較する最初の数。 T 型でなければなりません  
  
 [入力] `u`  
 比較する 2 番目の数値。 U 型です。 これでなければなりません  
  
## <a name="return-value"></a>戻り値  
 `true`場合`t`がより大きい`u`それ以外の`false`します。  
  
## <a name="remarks"></a>コメント  
 `SafeGreaterThan`2 つの異なる型の数値を比較することにより、正規の比較演算子を拡張します。  
  
 このメソッドの一部である[SafeInt ライブラリ](../windows/safeint-library.md)とは、単一の比較操作のインスタンスを作成せず、 [SafeInt クラス](../windows/safeint-class.md)です。  
  
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
 [SafeLessThan](../windows/safelessthan.md)   
 [SafeLessThanEquals](../windows/safelessthanequals.md)   
 [SafeGreaterThanEquals](../windows/safegreaterthanequals.md)