---
title: "Variable Argument Lists (...) (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "variable argument lists"
  - "parameter arrays"
ms.assetid: db1a27f4-02a8-4318-8690-1f2893f52b38
caps.latest.revision: 22
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Variable Argument Lists (...) (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

この例は、Visual C\+\+ で `...` 構文を使って可変個の引数を持つ関数を実装する方法を示しています。  
  
> [!NOTE]
>  これは C\+\+\/CLI に関するトピックです。  ISO 標準の C\+\+ での `...` の使用の詳細については、[楕円および可変値引数テンプレート](../cpp/ellipses-and-variadic-templates.md) および [省略記号と既定の引数](../misc/ellipses-and-default-arguments.md) を参照してください。  
  
 `...` を使用するパラメーターは、パラメーター リストの最後のパラメーターにする必要があります。  
  
## 例  
  
### コード  
  
```  
// mcppv2_paramarray.cpp  
// compile with: /clr  
using namespace System;  
double average( ... array<Int32>^ arr ) {  
   int i = arr->GetLength(0);  
   double answer = 0.0;  
  
   for (int j = 0 ; j < i ; j++)  
      answer += arr[j];  
  
   return answer / i;  
}  
  
int main() {  
   Console::WriteLine("{0}", average( 1, 2, 3, 6 ));  
}  
```  
  
### 出力  
  
```  
3  
```  
  
## コード例  
 次の例では、引数の数が可変である Visual C\+\+ の関数を C\# から呼び出す方法を示します。  
  
```  
// mcppv2_paramarray2.cpp  
// compile with: /clr:safe /LD  
using namespace System;  
  
public ref class C {  
public:   
   void f( ... array<String^>^ a ) {}  
};  
```  
  
 たとえば、関数 `f` は、可変個の引数を受け取ることができる関数であるかのように、C\# または Visual Basic から呼び出すことができます。  
  
 C\# では、`ParamArray` パラメーターに渡される引数は、可変個の引数で呼び出すことができます。  C\# でのコード例を次に示します。  
  
```  
// mcppv2_paramarray3.cs  
// compile with: /r:mcppv2_paramarray2.dll  
// a C# program  
  
public class X {  
   public static void Main() {  
      // Visual C# will generate a String array to match the   
      // ParamArray attribute  
      C myc = new C();  
      myc.f("hello", "there", "world");  
   }  
}  
```  
  
 Visual C\+\+ の `f` の呼び出しは、初期化された配列または可変長配列を渡すことができます。  
  
```  
// mcpp_paramarray4.cpp  
// compile with: /clr  
using namespace System;  
  
public ref class C {  
public:   
   void f( ... array<String^>^ a ) {}  
};  
  
int main() {  
   C ^ myc = gcnew C();  
   myc->f("hello", "world", "!!!");  
}  
```  
  
## 参照  
 [Arrays](../windows/arrays-cpp-component-extensions.md)