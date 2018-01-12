---
title: "方法: バイト配列にアンマネージ リソースを読み込む |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- native resources, loading into Byte array
- unmanaged resources, loading into Byte array
- native resources
ms.assetid: cdada6cd-6d42-437a-a90f-44a0b18d6a93
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a179934a0a94c552ea7dc81e3f4dbdc5a4458d70
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-load-unmanaged-resources-into-a-byte-array"></a>方法: アンマネージ リソースをバイト配列に読み込む
このトピックにアンマネージ リソースを読み込むためのいくつかの方法を説明する、<xref:System.Byte>配列。  
  
## <a name="example"></a>例  
 アンマネージ リソースのサイズがわかっている場合は、CLR 配列を事前に割り当てるし、CLR 配列の配列ブロックへのポインターを使用して配列に、リソースを読み込みます。  
  
```  
// load_unmanaged_resources_into_Byte_array.cpp  
// compile with: /clr  
using namespace System;  
void unmanaged_func( unsigned char * p ) {  
   for ( int i = 0; i < 10; i++ )  
      p[ i ] = i;  
}  
  
public ref class A {  
public:  
   void func() {  
      array<Byte> ^b = gcnew array<Byte>(10);  
      pin_ptr<Byte> p =  &b[ 0 ];  
      Byte * np = p;  
      unmanaged_func( np );   // pass pointer to the block of CLR array.  
      for ( int i = 0; i < 10; i++ )  
         Console::Write( b[ i ] );  
      Console::WriteLine();  
   }  
};  
  
int main() {  
   A^ g = gcnew A;  
   g->func();  
}  
```  
  
```Output  
0123456789  
```  
  
## <a name="example"></a>例  
 このサンプルでは、データをアンマネージ メモリ ブロックからマネージ配列にコピーする方法を示します。  
  
```  
// load_unmanaged_resources_into_Byte_array_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#include <string.h>  
int main() {  
   char buf[] = "Native String";  
   int len = strlen(buf);  
   array<Byte> ^byteArray = gcnew array<Byte>(len + 2);  
  
   // convert any native pointer to IntPtr by doing C-Style cast  
   Marshal::Copy( (IntPtr)buf, byteArray, 0, len );  
}  
```  
  
## <a name="see-also"></a>参照  
 [C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)