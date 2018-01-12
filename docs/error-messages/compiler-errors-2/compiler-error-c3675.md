---
title: "コンパイラ エラー C3675 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3675
dev_langs: C++
helpviewer_keywords: C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6545b7cfa8232ba8b48df104ce848eb34c0e108c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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