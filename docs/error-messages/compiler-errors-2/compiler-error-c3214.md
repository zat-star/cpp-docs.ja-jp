---
title: "コンパイラ エラー C3214 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3214
dev_langs: C++
helpviewer_keywords: C3214
ms.assetid: 49ee4a9a-2549-4adb-9d3a-38e154303c2e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6d280f500368ac7ac6ad0a987b987e1f9e57b6a5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3214"></a>コンパイラ エラー C3214
'type': ジェネリック 'generic_type' のジェネリック パラメーター 'param' の型引数が無効です。制約 'constraint' を満たしていません  
  
 ジェネリック クラスの制約を満たしていないジェネリック クラスをインスタンス化するために型を指定しました。  
  
 次の例では C3214 が生成されます。  
  
```  
// C3214.cpp  
// compile with: /clr  
interface struct A {};  
  
generic <class T>   
where T : A  
ref class C {};  
  
ref class X : public A {};  
  
int main() {  
   C<int>^ c = new C<int>;   // C3214  
   C<X ^> ^ c2 = new C<X^>;   // OK  
}  
```