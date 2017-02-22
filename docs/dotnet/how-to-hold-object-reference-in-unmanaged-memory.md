---
title: "方法: アンマネージ メモリ内にオブジェクト参照を保持する | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gcroot キーワード [C++], オブジェクト参照 (ネイティブ関数での)"
  - "オブジェクト参照, ネイティブ関数で"
  - "オブジェクト [C++], 参照 (ネイティブ関数での)"
  - "参照, ネイティブ関数内のオブジェクトを"
ms.assetid: a61eb8ce-3982-477d-8d3d-2173fd57166d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 方法: アンマネージ メモリ内にオブジェクト参照を保持する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

<xref:System.Runtime.InteropServices.GCHandle> をラップする gcroot.h を使用して、アンマネージ メモリ内に CLR オブジェクト参照を保持できます。  または、`GCHandle` を直接使用できます。  
  
## 使用例  
  
```  
// hold_object_reference.cpp  
// compile with: /clr  
#include "gcroot.h"  
using namespace System;  
  
#pragma managed  
class StringWrapper {  
  
private:  
   gcroot<String ^ > x;  
  
public:  
   StringWrapper() {  
      String ^ str = gcnew String("ManagedString");  
      x = str;  
   }  
  
   void PrintString() {  
      String ^ targetStr = x;  
      Console::WriteLine("StringWrapper::x == {0}", targetStr);  
   }  
};  
#pragma unmanaged  
int main() {  
   StringWrapper s;  
   s.PrintString();  
}  
```  
  
  **StringWrapper::x \=\= ManagedString**   
## 使用例  
 `GCHandle` は、アンマネージ メモリにマネージ オブジェクト参照を保持するための手段を提供します。<xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> メソッドを使用してマネージ オブジェクトへの非透過的ハンドルを作成し、<xref:System.Runtime.InteropServices.GCHandle.Free%2A> を使用してそのハンドルを解放します。  また、<xref:System.Runtime.InteropServices.GCHandle.Target%2A> メソッドを使用すると、マネージ コードのハンドルからオブジェクト参照をもう一度取得できます。  
  
```  
// hold_object_reference_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
class StringWrapper {  
   IntPtr m_handle;  
public:  
   StringWrapper() {  
      String ^ str = gcnew String("ManagedString");  
      m_handle = static_cast<IntPtr>(GCHandle::Alloc(str));  
   }  
   ~StringWrapper() {  
      static_cast<GCHandle>(m_handle).Free();  
   }  
  
   void PrintString() {  
      String ^ targetStr = safe_cast< String ^ >(static_cast<GCHandle>(m_handle).Target);  
      Console::WriteLine("StringWrapper::m_handle == {0}", targetStr);  
   }  
};  
  
#pragma unmanaged  
int main() {  
   StringWrapper s;   
   s.PrintString();  
}  
```  
  
  **StringWrapper::m\_handle \=\= ManagedString**   
## 参照  
 [C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)