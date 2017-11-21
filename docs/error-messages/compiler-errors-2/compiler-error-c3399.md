---
title: "コンパイラ エラー C3399 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3399
dev_langs: C++
helpviewer_keywords: C3399
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: abcf9e59df1562bd5b6b430c2c63554e87340abb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3399"></a>コンパイラ エラー C3399
'type' : ジェネリック パラメーターのインスタンスを作成するときに、引数を指定することはできません  
  
 `gcnew()` 制約を指定する場合は、制約型にパラメーターなしのコンストラクターがあることを指定します。 したがって、この型のインスタンスを作成してパラメーターを渡そうとすると、エラーになります。  
  
 参照してください[ジェネリック型パラメーターの制約 (C + + CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)詳細についてはします。  
  
## <a name="example"></a>例  
 次の例では C3399 が生成されます。  
  
```  
// C3399.cpp  
// compile with: /clr /c  
generic <class T>   
where T : gcnew()  
void f() {  
   T t = gcnew T(1);   // C3399  
   T t2 = gcnew T();   // OK  
}  
```