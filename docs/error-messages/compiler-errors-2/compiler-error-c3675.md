---
title: "コンパイラ エラー C3675 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3675
dev_langs:
- C++
helpviewer_keywords:
- C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d45236fc32fd0d10e9617b6946683d8ebd73ef0e
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3675"></a>コンパイラ エラー C3675
'function': 'property' が定義されているためには、予約されています  
  
 Get および set アクセサー メソッドと、コンパイラが生成単純なプロパティを宣言するときに名前が、プログラムのスコープ内に存在します。  コンパイラで生成された名前は、get _ と set _、プロパティ名に付加することによって形成されます。  そのため、コンパイラによって生成されたアクセサーと同じ名前を持つ関数を宣言できません。  
  
 詳細については、「 [property](../../windows/property-cpp-component-extensions.md) 」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、C3675 を生成します。  
  
```  
// C3675.cpp  
// compile with: /clr /c  
ref struct C {  
public:  
   property int Size;  
   int get_Size() { return 0; }   // C3675  
};  
```
