---
title: "コンパイラ エラー C2504 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2504
dev_langs:
- C++
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0463c762cec98f60b0e8a3811f1f5c9b7e2cdea7
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2504"></a>コンパイラ エラー C2504
'class': 基底クラスが定義されていません  
  
 基本クラスが宣言されていますが、定義されていることはありません。  以下の原因が考えられます。  
  
1.  インクルード ファイルがありません。  
  
2.  外部の基本クラスの宣言[extern](../../cpp/using-extern-to-specify-linkage.md)です。  
  
 次の例では、C2504 が生成されます。  
  
```  
// C2504.cpp  
// compile with: /c  
class A;  
class B : public A {};   // C2504  
```  
  
 わかりました  
  
```  
class C{};  
class D : public C {};  
```
