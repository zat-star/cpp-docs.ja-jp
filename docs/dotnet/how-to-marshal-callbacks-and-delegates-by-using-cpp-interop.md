---
title: "方法: C++ Interop を使用してコールバックおよびデリゲートをマーシャリングする | Microsoft Docs"
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
  - "C++ 相互運用機能, コールバックとデリゲート"
  - "コールバック [C++], マーシャリング"
  - "データ マーシャリング [C++], コールバックとデリゲート"
  - "デリゲート [C++], マーシャリング"
  - "相互運用 [C++], コールバックとデリゲート"
  - "マーシャリング [C++], コールバックとデリゲート"
ms.assetid: 2313e9eb-5df9-4367-be0f-14b4712d8d2d
caps.latest.revision: 23
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: C++ Interop を使用してコールバックおよびデリゲートをマーシャリングする
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、Visual C\+\+ を使用してマネージ コードとアンマネージ コード間でコールバックおよびデリゲート \(コールバックのマネージ バージョン\) をマーシャリングする方法を説明します。  
  
 次のコード例では、[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md) の \#pragma ディレクティブを使用してマネージ関数とアンマネージ関数を同じファイル内で実装していますが、これらの関数は、別個のファイルに定義することもできます。  アンマネージ関数のみを含むファイルは、[\/clr \(共通言語ランタイムのコンパイル\)](../build/reference/clr-common-language-runtime-compilation.md) でコンパイルする必要はありません。  
  
## 使用例  
 次の例は、マネージ デリゲートを発生させるためにアンマネージ API を構成する方法を示します。  マネージ デリケートが作成され、相互運用メソッドの 1 つ \(<xref:System.Runtime.InteropServices.Marshal.GetFunctionPointerForDelegate%2A>\) を使用して、デリゲートの基になるエントリ ポイントを取得します。  次に、このアドレスは、アンマネージ関数に渡されます。アンマネージ関数は、自身がマネージ関数として実装されていることを認識せずにこのアドレスを呼び出します。  
  
 デリゲートを再配置したり、ガベージ コレクターで破棄されることを回避するために、[pin\_ptr \(C\+\+\/CLI\)](../Topic/pin_ptr%20\(C++-CLI\).md) を使用してデリゲートを固定することはできますが、その必要はありません。  早すぎるガベージ コレクションからデリゲートを保護することは必要ですが、デリゲートを固定すると、デリゲートが必要以上に保護され、コレクションを実行できなくなるだけでなく再配置もできなくなります。  
  
 ガベージ コレクションによってデリゲートを再配置する場合、デリゲートの基になるマネージ コールバックには影響しません。したがって、<xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> を使用してデリゲートへの参照を追加すると、デリゲートの再配置は可能になりますが、デリゲートの破棄は回避できます。  pin\_ptr の代わりに GCHandle を使用すると、マネージ ヒープでのフラグメントの可能性を削減できます。  
  
```  
// MarshalDelegate1.cpp  
// compile with: /clr  
#include <iostream>  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
// Declare an unmanaged function type that takes two int arguments  
// Note the use of __stdcall for compatibility with managed code  
typedef int (__stdcall *ANSWERCB)(int, int);  
  
int TakesCallback(ANSWERCB fp, int n, int m) {  
   printf_s("[unmanaged] got callback address, calling it...\n");  
   return fp(n, m);  
}  
  
#pragma managed  
  
public delegate int GetTheAnswerDelegate(int, int);  
  
int GetNumber(int n, int m) {  
   Console::WriteLine("[managed] callback!");  
   return n + m;  
}  
  
int main() {  
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);  
   GCHandle gch = GCHandle::Alloc(fp);  
   IntPtr ip = Marshal::GetFunctionPointerForDelegate(fp);  
   ANSWERCB cb = static_cast<ANSWERCB>(ip.ToPointer());  
   Console::WriteLine("[managed] sending delegate as callback...");  
  
// force garbage collection cycle to prove  
// that the delegate doesn't get disposed  
   GC::Collect();  
  
   int answer = TakesCallback(cb, 243, 257);  
  
// release reference to delegate  
   gch.Free();  
}  
```  
  
## 使用例  
 次の例は、上の例に類似していますが、この場合は、指定した関数ポインターはアンマネージ API によって格納されるので、随時この関数ポインターを呼び出して、任意の期間ガベージ コレクションを抑止することを要求できます。  その結果、次の例は、<xref:System.Runtime.InteropServices.GCHandle> のグローバル インスタンスを使用して、関数のスコープに関係なくデリゲートが再配置されることを防ぎます。  最初の例で説明したとおり、これらの例では pin\_ptr を使用する必要はありませんが、使用したとしても、この場合 pin\_ptr のスコープが単一の関数に制限されているため、動作しません。  
  
```  
// MarshalDelegate2.cpp  
// compile with: /clr   
#include <iostream>  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
// Declare an unmanaged function type that takes two int arguments  
// Note the use of __stdcall for compatibility with managed code  
typedef int (__stdcall *ANSWERCB)(int, int);  
static ANSWERCB cb;  
  
int TakesCallback(ANSWERCB fp, int n, int m) {  
   cb = fp;  
   if (cb) {  
      printf_s("[unmanaged] got callback address (%d), calling it...\n", cb);  
      return cb(n, m);  
   }  
   printf_s("[unmanaged] unregistering callback");  
   return 0;  
}  
  
#pragma managed  
  
public delegate int GetTheAnswerDelegate(int, int);  
  
int GetNumber(int n, int m) {  
   Console::WriteLine("[managed] callback!");  
   static int x = 0;  
   ++x;  
  
   return n + m + x;  
}  
  
static GCHandle gch;  
  
int main() {  
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);  
  
   gch = GCHandle::Alloc(fp);  
  
   IntPtr ip = Marshal::GetFunctionPointerForDelegate(fp);  
   ANSWERCB cb = static_cast<ANSWERCB>(ip.ToPointer());  
   Console::WriteLine("[managed] sending delegate as callback...");  
  
   int answer = TakesCallback(cb, 243, 257);  
  
   // possibly much later (in another function)...  
  
   Console::WriteLine("[managed] releasing callback mechanisms...");  
   TakesCallback(0, 243, 257);  
   gch.Free();  
}  
```  
  
## 参照  
 [C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)