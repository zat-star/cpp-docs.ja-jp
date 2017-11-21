---
title: "コンパイラ エラー C3420 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3420
dev_langs: C++
helpviewer_keywords: C3420
ms.assetid: 99b53c77-f36b-4574-9199-b53111becccb
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b0f17a1dc713940cfb18ff05af71b69f3e4df516
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3420"></a>コンパイラ エラー C3420
'finalizer' : ファイナライザーを仮想にすることはできません  
  
 ファイナライザーは、それを囲む型から非仮想的にのみ呼び出すことができます。 したがって、仮想のファイナライザーを宣言すると、エラーになります。  
  
 詳細については、次を参照してください。[する方法のデストラクターおよびファイナライザー: を定義およびクラスと構造体を使用 (C + + CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)です。  
  
## <a name="example"></a>例  
 次の例では C3420 が生成されます。  
  
```  
// C3420.cpp  
// compile with: /clr /c  
ref class R {  
   virtual !R() {}   // C3420  
};  
```