---
title: "コンパイラの警告 (レベル 4) C4564 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4564
dev_langs:
- C++
helpviewer_keywords:
- C4564
ms.assetid: 555b301b-313e-4262-9f81-eb878674be60
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 25f9f8755acafd71a9ac75a68f601660b781746a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4564"></a>コンパイラの警告 (レベル 4) C4564
メソッド 'method' クラス 'class' のサポートされていない既定のパラメーター 'parameter' の定義します。  
  
 既定値を持つ 1 つまたは複数のパラメーターを持つメソッドが検出されました。 メソッドが呼び出される; パラメーターの既定値は無視されます。これらのパラメーターの値を明示的に指定します。 これらのパラメーターの値を明示的に指定しないと、C++ コンパイラでエラーが生成されます。  
  
 Visual Basic で作成された次 .dll、指定したメソッドの引数に対して既定のパラメーター作成できます。  
  
```  
' C4564.vb  
' compile with: vbc /t:library C4564.vb  
Public class TestClass  
   Public Sub MyMethod (a as Integer, _  
                        Optional c as Integer=1)  
   End Sub  
End class  
```  
  
 Visual Basic で作成された .dll ファイルを使用して次の C++ のサンプル  
  
```  
// C4564.cpp  
// compile with: /clr /W4 /WX  
#using <C4564.dll>  
  
int main() {  
   TestClass ^ myx = gcnew TestClass();   // C4564  
   myx->MyMethod(9);  
   // try the following line instead, to avoid an error  
   // myx->MyMethod(9, 1);  
}  
```