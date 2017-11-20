---
title: "コンパイラ エラー C3454 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3454
dev_langs: C++
helpviewer_keywords: C3454
ms.assetid: dc4e6d57-5b4d-4114-8d6f-22f9ae62925b
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 026b77ca4f9488c1178a2815ffb0a9c7c71bdf54
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3454"></a>コンパイラ エラー C3454
[attribute] はクラス宣言では使用できません  
  
 クラスは、属性になるように定義する必要があります。  
  
 詳細については、「 [attribute](../../windows/attribute.md)」を参照してください。  
  
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