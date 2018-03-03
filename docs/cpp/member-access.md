---
title: "メンバー アクセス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- member-selection operators [C++]
- pointers, smart
- member access, overloaded operators
- operator overloading [C++], member access operators
- smart pointers, definition
- smart pointers
ms.assetid: 8c7b2c43-eb92-4d42-9a8e-61aa37d71333
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 18348c3d59457b7920f7902687f0220121c30e2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="member-access"></a>メンバー アクセス
メンバー アクセス演算子をオーバー ロードがクラス メンバーへのアクセスを制御できます (**->**)。 この演算子は、この使用方法では単項演算子と見なされ、オーバーロードされる演算子関数は、クラス メンバー関数である必要があります。 したがって、このような関数の宣言は次のとおりです。  
  
## <a name="syntax"></a>構文  
  
```  
  
class-type *operator->()  
```  
  
## <a name="remarks"></a>コメント  
 ここで*クラス型*このオペレーターが所属するクラスの名前を指定します。 メンバー アクセス演算子関数は、非静的メンバー関数である必要があります。  
  
 この演算子は、逆参照やカウントの使用の前にポインターを検証する "スマート ポインター" を実装するために使用されます (多くの場合はポインターの逆参照演算子と共に)。  
  
 **.** メンバー アクセス演算子はオーバー ロードできません。  
  
## <a name="see-also"></a>参照  
 [演算子のオーバーロード](../cpp/operator-overloading.md)