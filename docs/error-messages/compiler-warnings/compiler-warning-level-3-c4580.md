---
title: "コンパイラの警告 (レベル 3) C4580 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4580
dev_langs:
- C++
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: b551b1a7e0ae03a7de5108a1d114155786972847
ms.openlocfilehash: c8cebbda1d3472a2efda43f816e7a13f2f460408
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4580"></a>コンパイラの警告 (レベル 3) C4580
[attribute] は使用できません。System::Attribute または Platform::Metadata を基底クラスとして指定してください  
  
[[属性](../../windows/attribute.md)] が不要になったのユーザー定義の属性を作成するための構文をお勧めします。 詳細については、次を参照してください。[ユーザー定義属性](../../windows/user-defined-attributes-cpp-component-extensions.md)します。 CLR コードの場合は、`System::Attribute` から属性を派生させます。 Windows ランタイム コードの場合は、`Platform::Metadata` から属性を派生させます。  
  
## <a name="example"></a>例  
次の例では、C3454 を生成し、その修正方法を示しています。  
  
```cpp  
// C4580.cpp  
// compile with: /W3 /c /clr  
[attribute]   // C4580  
public ref class Attr {  
public:  
   int m_t;  
};  
  
public ref class Attr2 : System::Attribute {  
public:  
   int m_t;  
};  
```
