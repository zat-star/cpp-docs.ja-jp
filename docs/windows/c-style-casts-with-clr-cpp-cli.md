---
title: "C-Style Casts with /clr (C++/CLI) | Microsoft Docs"
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
  - "C-style casts and /clr"
ms.assetid: d2a4401a-156a-4da9-8d12-923743e26913
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C-Style Casts with /clr (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次のトピックでは、共通言語ランタイムにのみ適用されます。  
  
 CLR を使用すると、コンパイラは次の順序で、次に示すキャストの 1 つがに C スタイルのキャストをマップしようと入力します:  
  
1.  const\_cast  
  
2.  safe\_cast  
  
3.  const\_cast safe\_cast と  
  
4.  static\_cast  
  
5.  const\_cast と static\_cast  
  
 キャストの None 上のリストは、式、および対象の種類は CLR 参照型である場合、C スタイルは、ランタイム チェック \(castclass MSIL 命令\) にマップをキャストしました。  それ以外の場合は".のスタイルのキャストは無効問題、コンパイラ エラーになります。  
  
## 解説  
 C.のスタイルのキャストはお勧めしません。  [\/clr \(共通言語ランタイムのコンパイル\)](../build/reference/clr-common-language-runtime-compilation.md)でコンパイルする場合は、[safe\_cast](../windows/safe-cast-cpp-component-extensions.md)を使用します。  
  
 次の例は、.に `const_cast`にマップするスタイルのキャストを示します。  
  
```  
// cstyle_casts_1.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct R {};  
int main() {  
   const R^ constrefR = gcnew R();  
   R^ nonconstR = (R^)(constrefR);   
}  
```  
  
 次の例は、.に `safe_cast`にマップするスタイルのキャストを示します。  
  
```  
// cstyle_casts_2.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Object ^ o = "hello";  
   String ^ s = (String^)o;  
}  
```  
  
 次の例は、.に `const_cast`と `safe_cast` にマップするスタイルのキャストを示します。  
  
```  
// cstyle_casts_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct R {};  
ref struct R2 : public R {};  
  
int main() {  
   const R^ constR2 = gcnew R2();  
   try {  
   R2^ b2DR = (R2^)(constR2);  
   }  
   catch(InvalidCastException^ e) {  
      System::Console::WriteLine("Invalid Exception");  
   }  
}  
```  
  
 次の例は、.に `static_cast`にマップするスタイルのキャストを示します。  
  
```  
// cstyle_casts_4.cpp  
// compile with: /clr  
using namespace System;  
  
struct N1 {};  
struct N2 {  
   operator N1() {  
      return N1();  
   }  
};  
  
int main() {  
   N2 n2;  
   N1 n1 ;  
   n1 = (N1)n2;  
}  
```  
  
 次の例は、.に `const_cast`と `static_cast` にマップするスタイルのキャストを示します。  
  
```  
// cstyle_casts_5.cpp  
// compile with: /clr  
using namespace System;  
struct N1 {};  
  
struct N2 {  
   operator const N1*() {  
      static const N1 n1;  
      return &n1;  
   }  
};  
  
int main() {  
   N2 n2;  
   N1* n1 = (N1*)(const N1*)n2;   // const_cast + static_cast  
}  
```  
  
 次の例は、.にランタイム チェックにマップするスタイルのキャストを示します。  
  
```  
// cstyle_casts_6.cpp  
// compile with: /clr  
using namespace System;  
  
ref class R1 {};  
ref class R2 {};  
  
int main() {  
   R1^ r  = gcnew R1();  
   try {  
      R2^ rr = ( R2^)(r);  
   }  
   catch(System::InvalidCastException^ e) {  
      Console::WriteLine("Caught expected exception");  
   }  
}  
```  
  
 次の例は、コンパイラがエラーを生成します。無効な C スタイルのキャストを示します。  
  
```  
// cstyle_casts_7.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String^s = S"hello";  
   int i = (int)s;   // C2440  
}  
```  
  
## 要件  
 コンパイラ オプション: **\/clr**  
  
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)