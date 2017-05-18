---
title: "コンパイラ エラー C3454 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3454
dev_langs:
- C++
helpviewer_keywords:
- C3454
ms.assetid: dc4e6d57-5b4d-4114-8d6f-22f9ae62925b
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 68d0930b7c80dfa997eddb55b01f9d9c313b611e
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3454"></a>コンパイラ エラー C3454
[attribute] はクラス宣言では使用できません  
  
 クラスは、属性になるように定義する必要があります。  
  
 詳細については、次を参照してください。[属性](../../windows/attribute.md)です。  
  
## <a name="example"></a>例  
 次の例では C3454 が生成されます。  
  
```  
// C3454.cpp  
// compile with: /clr /c  
using namespace System;  
  
[attribute]   // C3454  
ref class Attr1;  
  
[attribute]   // OK  
ref class Attr2 {};  
```
