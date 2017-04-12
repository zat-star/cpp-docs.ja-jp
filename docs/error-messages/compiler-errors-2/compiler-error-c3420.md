---
title: "コンパイラ エラー C3420 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3420
dev_langs:
- C++
helpviewer_keywords:
- C3420
ms.assetid: 99b53c77-f36b-4574-9199-b53111becccb
caps.latest.revision: 3
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 7a6d4806b26fe152cacd61696f405c19a7d49cee
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3420"></a>コンパイラ エラー C3420
'finalizer' : ファイナライザーを仮想にすることはできません  
  
 ファイナライザーは、それを囲む型から非仮想的にのみ呼び出すことができます。 したがって、仮想のファイナライザーを宣言すると、エラーになります。  
  
 詳細については、次を参照してください。[する方法のデストラクターおよびファイナライザー: クラスと構造体定義および使用 (C + +/CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)します。  
  
## <a name="example"></a>例  
 次の例では C3420 が生成されます。  
  
```  
// C3420.cpp  
// compile with: /clr /c  
ref class R {  
   virtual !R() {}   // C3420  
};  
```
