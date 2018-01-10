---
title: "コンパイラ エラー C2920 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2920
dev_langs: C++
helpviewer_keywords: C2920
ms.assetid: 0a4cb2de-00a0-4209-8160-c7ce6ed7d9ab
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ba5a7706dc4607897cb2ef71f2072209e0516f53
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2920"></a>コンパイラ エラー C2920
再定義 : 'class' : クラス テンプレートまたはジェネリックは既に 'type' として宣言されています  
  
 ジェネリックまたはテンプレート クラスに複数の宣言が存在しますが、これらは同じではありません。 このエラーを修正するには、型ごとに異なる名前を使用するか、型名の再定義を削除します。  
  
 次の例では、C2920 を生成し、その修正方法を示しています。  
  
```  
// C2920.cpp  
// compile with: /c  
typedef int TC1;  
template <class T>   
struct TC1 {};   // C2920  
struct TC2 {};   // OK - fix by using a different name  
```  
  
 C2920 は、ジェネリックを使用する場合にも発生することがあります。  
  
```  
// C2920b.cpp  
// compile with: /clr /c  
typedef int GC1;  
generic <class T>   
ref struct GC1 {};   // C2920  
ref struct GC2 {};   // OK - fix by using a different name  
```