---
title: "コンパイラ エラー C3246 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3246
dev_langs:
- C++
helpviewer_keywords:
- C3246
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 262dc8bde5dcb4c12909c69bce3fa867685245eb
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3246"></a>コンパイラ エラー C3246
'class': 'type' から継承できません。'sealed' として宣言されている理由によります。  
  
[sealed](../../windows/sealed-cpp-component-extensions.md) としてマークされているクラスは、他のクラスの基底クラスになることはできません。  
  
次の例では C3246 が生成されます。  
  
```  
// C3246_2.cpp  
// compile with: /clr /LD  
ref class X sealed {};  
  
ref class Y : public X {}; // C3246  
```  

