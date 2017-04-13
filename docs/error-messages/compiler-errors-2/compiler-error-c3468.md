---
title: "コンパイラ エラー C3468 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3468
dev_langs:
- C++
helpviewer_keywords:
- C3468
ms.assetid: cfd320db-2f6e-4e0d-ba02-e79ece87e1e0
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 8e48b9318d7e461900124bcd491d584dbd73e0e8
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3468"></a>コンパイラ エラー C3468
'type': 型は次のアセンブリにのみ転送できます:   
  
 '`file`' はアセンブリではありません  
  
 アセンブリ内の型のみを転送することができます。  
  
 詳細については、次を参照してください。 [Type Forwarding (C + + CLI)](../../windows/type-forwarding-cpp-cli.md)です。  
  
## <a name="example"></a>例  
 モジュールを作成する例を次に示します。  
  
```  
// C3468.cpp  
// compile with: /LN /clr  
public ref class R {};  
```  
  
## <a name="example"></a>例  
 次の例では C3468 が生成されます。  
  
```  
// C3468_b.cpp  
// compile with: /clr /c  
#using "C3468.netmodule"  
[ assembly:TypeForwardedTo(R::typeid) ];   // C3468  
```
