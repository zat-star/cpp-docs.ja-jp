---
title: "コンパイラ エラー C3291 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3291
dev_langs:
- C++
helpviewer_keywords:
- C3291
ms.assetid: ed2e9f89-8dbc-4387-bc26-cc955e840858
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: da6145b3a3aecd5f550a58c009020fb24280349e
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3291"></a>コンパイラ エラー C3291
'default': trivial プロパティの名前にすることはできません  
  
 trivial プロパティに `default`という名前を付けることはできません。 詳細については、「 [property](../../windows/property-cpp-component-extensions.md) 」を参照してください。  
  
## <a name="example"></a>例  
 次の例では C3291 が生成されます。  
  
```  
// C3291.cpp  
// compile with: /clr /c  
ref struct C {  
   property System::String ^ default;   // C3291  
   property System::String ^ Default;   // OK  
};  
```
