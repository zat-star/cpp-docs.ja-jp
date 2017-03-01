---
title: "コンパイラ エラー C3467 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3467
dev_langs:
- C++
helpviewer_keywords:
- C3467
ms.assetid: e2b844d0-4920-412f-99fd-cd8051c4aa41
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: edea758c567f74202c12f7ee1391fb3f12faa980
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3467"></a>コンパイラ エラー C3467
'type': この型は既に転送されました  
  
 同じ型の事前宣言が複数検出されました。 宣言は、型ごとに&1; 回しかできません。  
  
 詳細については、次を参照してください。[型の転送 (C + +/CLI)](../../windows/type-forwarding-cpp-cli.md)します。  
  
## <a name="example"></a>例  
 コンポーネントを作成する例を次に示します。  
  
```  
// C3467.cpp  
// compile with: /LD /clr  
public ref class R {};  
```  
  
## <a name="example"></a>例  
 次の例では C3467 が生成されます。  
  
```  
// C3467_b.cpp  
// compile with: /clr /c  
#using "C3467.dll"  
[ assembly:TypeForwardedTo(R::typeid) ];  
[ assembly:TypeForwardedTo(R::typeid) ];   // C3467  
```
