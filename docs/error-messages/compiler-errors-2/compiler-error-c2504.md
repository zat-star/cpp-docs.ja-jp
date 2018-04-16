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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3b7843d69b7238bedb58d0232d64ff2d0a826d07
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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