---
title: "方法: C++ Interop を使用して COM 文字列をマーシャリングする | Microsoft Docs"
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
  - "COM [C++], マーシャリング (文字列の)"
  - "データ マーシャリング [C++], 文字列"
  - "相互運用 [C++], 文字列"
  - "マーシャリング [C++], 文字列"
ms.assetid: 06590759-bf99-4e34-a3a9-4527ea592cc2
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: C++ Interop を使用して COM 文字列をマーシャリングする
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、マネージ関数とアンマネージ関数の間で BSTR \(COM プログラミングで推奨される基本文字列形式\) を渡す方法を説明します。  その他の文字列型との相互運用については、次のトピックを参照してください。  
  
-   [方法: C\+\+ Interop を使用して Unicode 文字列をマーシャリングする](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [方法: C\+\+ Interop を使用して ANSI 文字列をマーシャリングする](../Topic/How%20to:%20Marshal%20ANSI%20Strings%20Using%20C++%20Interop.md)  
  
 次のコード例では、[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md) の \#pragma ディレクティブを使用してマネージ関数とアンマネージ関数を同じファイル内で実装していますが、これらの関数は、別個のファイルに定義された場合も同じように相互運用できます。  アンマネージ関数のみを含むファイルは、[\/clr \(共通言語ランタイムのコンパイル\)](../build/reference/clr-common-language-runtime-compilation.md) でコンパイルする必要はありません。  
  
## 使用例  
 次の例は、マネージ関数からアンマネージ関数に BSTR \(COM プログラミングで使用される文字列形式\) を渡す方法を示しています。  呼び出し元のマネージ関数は、<xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> を使用して、.NET System.String のコンテンツの BSTR 表現のアドレスを取得します。  このポインターは、アンマネージ関数の実行中にガベージ コレクション サイクルでその物理アドレスが変更されないように、[pin\_ptr \(C\+\+\/CLI\)](../Topic/pin_ptr%20\(C++-CLI\).md) を使用して固定されます。  ガベージ コレクターは、[pin\_ptr \(C\+\+\/CLI\)](../Topic/pin_ptr%20\(C++-CLI\).md) が適用範囲の外になるまでメモリを移動できません。  
  
```  
// MarshalBSTR1.cpp  
// compile with: /clr  
#define WINVER 0x0502  
#define _AFXDLL  
#include <afxwin.h>  
  
#include <iostream>  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
void NativeTakesAString(BSTR bstr) {  
   printf_s("%S", bstr);  
}  
  
#pragma managed  
  
int main() {  
   String^ s = "test string";  
  
   IntPtr ip = Marshal::StringToBSTR(s);  
   BSTR bs = static_cast<BSTR>(ip.ToPointer());  
   pin_ptr<BSTR> b = &bs;  
  
   NativeTakesAString( bs );  
   Marshal::FreeBSTR(ip);  
}  
```  
  
## 使用例  
 次の例は、アンマネージ関数からアンマネージ関数に BSTR を渡す方法を示しています。  受信側のマネージ関数は、その文字列を BSTR として使用したり、または他のマネージ関数と併用するために <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> を使用して <xref:System.String> に変換したりできます。  BSTR を表すメモリはアンマネージ ヒープに割り当てられ、またアンマネージ ヒープ上にはガベージ コレクションが存在しないため、固定の必要はありません。  
  
```  
// MarshalBSTR2.cpp  
// compile with: /clr  
#define WINVER 0x0502  
#define _AFXDLL  
#include <afxwin.h>  
  
#include <iostream>  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
  
void ManagedTakesAString(BSTR bstr) {  
   String^ s = Marshal::PtrToStringBSTR(static_cast<IntPtr>(bstr));  
   Console::WriteLine("(managed) convered BSTR to String: '{0}'", s);  
}  
  
#pragma unmanaged  
  
void UnManagedFunc() {  
   BSTR bs = SysAllocString(L"test string");  
   printf_s("(unmanaged) passing BSTR to managed func...\n");  
   ManagedTakesAString(bs);  
}  
  
#pragma managed  
  
int main() {  
   UnManagedFunc();  
}  
```  
  
## 参照  
 [C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)