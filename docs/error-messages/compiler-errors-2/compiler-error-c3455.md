---
title: "コンパイラ エラー C3455 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3455
dev_langs: C++
helpviewer_keywords: C3455
ms.assetid: 218e5cfe-5391-4eeb-81c2-85c47e3a6cd2
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 079bdea18bade971ee972f6bb8d09e79965baddc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3455"></a>コンパイラ エラー C3455
'attribute': どの属性コンストラクターも引数に一致しませんでした  
  
 無効な値が属性の宣言に使用されました。  詳細については、「 [attribute](../../windows/attribute.md) 」を参照してください。  
  
## <a name="example"></a>例  
 次の例では C3455 が生成されます。  
  
```  
// C3455.cpp  
// compile with: /clr /c  
using namespace System;  
  
[attribute("MyAt")]   // C3455  
// try the following line instead  
// [attribute(All)]  
ref struct MyAttr {  
   MyAttr() {}  
};  
```