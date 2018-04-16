---
title: "コンパイラの警告 (レベル 1) C4540 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4540
dev_langs:
- C++
helpviewer_keywords:
- C4540
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aaaef1edaa6af093ae03fe69231a9686e3d087a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4540"></a>コンパイラの警告 (レベル 1) C4540
dynamic_cast がアクセスできないか、あいまいなベース; に変換するために使用実行時のテストは失敗し ('type2' への ' type1')  
  
 使用する`dynamic_cast`を 1 つの型から変換します。 コンパイラでは、キャストが失敗は常に決定されます (返す**NULL**) 基底クラスにアクセスできないため (`private`のインスタンス) あいまいな (複数回表示されるクラスの階層内のインスタンス) またはします。  
  
 この警告の例を次に示します。 クラス**B**クラスから派生した**A**です。プログラムを使用して`dynamic_cast`クラスにキャストする**B** (派生クラス) クラスに**A**、これは必ず失敗クラス**B**は`private`およびこのインターフェイスアクセス不可能です。 アクセスを変更する**A**に**パブリック**警告を解決します。  
  
```  
// C4540.cpp  
// compile with: /W1  
  
struct A {   
   virtual void g() {}  
};  
  
struct B : private A {  
   virtual void g() {}  
};  
  
int main() {  
   B b;  
   A * ap = dynamic_cast<A*>(&b);   // C4540  
}  
```