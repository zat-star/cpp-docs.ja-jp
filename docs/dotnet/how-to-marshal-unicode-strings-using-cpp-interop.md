---
title: "方法: C++ Interop を使用して Unicode 文字列をマーシャリングする | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ 相互運用機能, 文字列"
  - "データ マーシャリング [C++], 文字列"
  - "相互運用 [C++], 文字列"
  - "マーシャリング [C++], 文字列"
  - "Unicode, マーシャリング (文字列の)"
ms.assetid: 96c2141d-6c5d-43ef-a1aa-5785afb9a9aa
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: C++ Interop を使用して Unicode 文字列をマーシャリングする
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、Visual C\+\+ の相互運用性の 1 つのファセットについて説明します。  詳細については、「[C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)」を参照してください。  
  
 次のコード例では、[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md) の \#pragma ディレクティブを使用してマネージ関数とアンマネージ関数を同じファイル内で実装していますが、これらの関数は、別個のファイルに定義された場合も同じように相互運用できます。  アンマネージ関数のみを含むファイルは、[\/clr \(共通言語ランタイムのコンパイル\)](../build/reference/clr-common-language-runtime-compilation.md) でコンパイルする必要はありません。  
  
 このトピックでは、マネージ関数とアンマネージ関数の間で Unicode 文字列を渡す方法について説明します。  その他の文字列型との相互運用については、次のトピックを参照してください。  
  
-   [方法: C\+\+ Interop を使用して ANSI 文字列をマーシャリングする](../Topic/How%20to:%20Marshal%20ANSI%20Strings%20Using%20C++%20Interop.md)  
  
-   [方法: C\+\+ Interop を使用して COM 文字列をマーシャリングする](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)  
  
## 使用例  
 マネージ関数からアンマネージ関数に Unicode 文字列を渡すには、PtrToStringChars 関数 \(Vcclr.h で宣言\) を使用して、マネージ文字列が格納されているメモリにアクセスします。  このアドレスはネイティブ関数に渡されるため、アンマネージ関数の実行中にガベージ コレクション サイクルを発生する場合、[pin\_ptr \(C\+\+\/CLI\)](../Topic/pin_ptr%20\(C++-CLI\).md) でメモリを固定して、文字列データが再配置されないようにすることが重要となります。  
  
```  
// MarshalUnicode1.cpp  
// compile with: /clr  
#include <iostream>  
#include <stdio.h>  
#include <vcclr.h>  
  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
void NativeTakesAString(const wchar_t* p) {  
   printf_s("(native) received '%S'\n", p);  
}  
  
#pragma managed  
  
int main() {  
   String^ s = gcnew String("test string");  
   pin_ptr<const wchar_t> str = PtrToStringChars(s);  
  
   Console::WriteLine("(managed) passing string to native func...");  
   NativeTakesAString( str );  
}  
```  
  
## 使用例  
 アンマネージ関数によって呼び出されるマネージ関数内の Unicode 文字列にアクセスするために必要なデータのマーシャリングを次の例に示します。  マネージ関数は、ネイティブな Unicode 文字列を受け取ると、<xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> メソッドを使用して、それをマネージ文字列に変換します。  
  
```  
// MarshalUnicode2.cpp  
// compile with: /clr  
#include <iostream>  
  
using namespace std;  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
  
void ManagedStringFunc(wchar_t* s) {  
   String^ ms = Marshal::PtrToStringUni((IntPtr)s);  
   Console::WriteLine("(managed) received '{0}'", ms);  
}  
  
#pragma unmanaged  
  
void NativeProvidesAString() {  
   cout << "(unmanaged) calling managed func...\n";  
   ManagedStringFunc(L"test string");  
}  
  
#pragma managed  
  
int main() {  
   NativeProvidesAString();  
}  
```  
  
## 参照  
 [C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)