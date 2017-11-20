---
title: "typeof が t::typeid へ移動 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- typeid operator
- __typeof keyword
- typeid keyword [C++]
ms.assetid: 6a0d35a7-7a1a-4070-b187-cff37cfdc205
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 90c75b67dc6496f51d335f83a49242b7f7ae0b29
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="typeof-goes-to-ttypeid"></a>typeof から T::typeid への移行
`typeof` C++ に置き換わる可能性されてのマネージ拡張で使用する演算子、 `typeid` Visual C でキーワード。  
  
 マネージ拡張で、`__typeof()`演算子は、関連付けられている返します`Type*`オブジェクトのマネージ型の名前が渡されるときにします。 例:  
  
```  
// Creates and initializes a new Array instance.  
Array* myIntArray =   
   Array::CreateInstance( __typeof(Int32), 5 );  
```  
  
 新しい構文で`__typeof`が別の形式ので置き換えられた`typeid`を返す、`Type^`マネージ型が指定されている場合。  
  
```  
// Creates and initializes a new Array instance.  
Array^ myIntArray =   
   Array::CreateInstance( Int32::typeid, 5 );  
```  
  
## <a name="see-also"></a>関連項目  
 [一般的な言語の変更 (C + + CLI)](../dotnet/general-language-changes-cpp-cli.md)   
 [typeid](../windows/typeid-cpp-component-extensions.md)