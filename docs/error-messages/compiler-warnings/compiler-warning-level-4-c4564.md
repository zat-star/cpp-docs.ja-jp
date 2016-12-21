---
title: "コンパイラの警告 (レベル 4) C4564 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4564"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4564"
ms.assetid: 555b301b-313e-4262-9f81-eb878674be60
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4564
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

メソッド 'メソッド' \(クラス 'クラス'\) は、サポートのない既定のパラメーター 'パラメーター' を定義します  
  
 1 つ以上のパラメーターに既定値のあるメソッドが見つかりました。  メソッドが呼び出されるとき、パラメーターの既定値は無視されます。これらのパラメーターの値を明示的に指定してください。  パラメーターの値を明示的に指定しないと、C\+\+ コンパイラではエラーが生成されます。  
  
 次の .dll は Visual Basic で作成されており、メソッドの引数に既定のパラメーターを使用できます。  
  
```  
' C4564.vb  
' compile with: vbc /t:library C4564.vb  
Public class TestClass  
   Public Sub MyMethod (a as Integer, _  
                        Optional c as Integer=1)  
   End Sub  
End class  
```  
  
 また、次の C\+\+ のサンプルでは、Visual Basic で作成された .dll を使用しています。  
  
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