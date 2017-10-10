---
title: "コンパイラ エラー C3116 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3116
dev_langs:
- C++
helpviewer_keywords:
- C3116
ms.assetid: 597463e1-a5cc-4ed3-a917-eae9a61d3312
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c9503250dd6ff165f6a955d36ebfe38f0715e422
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3116"></a>コンパイラ エラー C3116
'ストレージの指定子': インターフェイス メソッドに対する無効なストレージ クラス  
  
 使用する`typedef`、 `register`、または`static`インターフェイス メソッドのストレージ クラスとして。 これらのストレージ クラスは、インターフェイスのメンバーには使用できません。  
  
 次の例では、C3116 が生成されます。  
  
```  
// C3116.cpp  
__interface ImyInterface  
{  
   static void myFunc();   // C3116  
};  
```
