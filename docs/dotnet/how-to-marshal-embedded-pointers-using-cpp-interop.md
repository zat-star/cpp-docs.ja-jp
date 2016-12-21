---
title: "方法: C++ Interop を使用して埋め込みポインターをマーシャリングする | Microsoft Docs"
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
  - "C++ 相互運用機能, 埋め込みポインター"
  - "データ マーシャリング [C++], 埋め込みポインター"
  - "相互運用 [C++], 埋め込みポインター"
  - "マーシャリング [C++], 埋め込みポインター"
  - "ポインター [C++], マーシャリング"
  - "構造体 [C++], マーシャリング (埋め込みポインターの)"
ms.assetid: 05fb8858-97f2-47aa-86b2-2c0ad713bdb2
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: C++ Interop を使用して埋め込みポインターをマーシャリングする
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次のコード例では、[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md) の \#pragma ディレクティブを使用してマネージ関数とアンマネージ関数を同じファイル内で実装していますが、これらの関数は、別個のファイルに定義された場合も同じように相互運用できます。  アンマネージ関数のみを含むファイルは、[\/clr \(共通言語ランタイムのコンパイル\)](../build/reference/clr-common-language-runtime-compilation.md) でコンパイルする必要はありません。  
  
## 使用例  
 次の例は、ポインターを含む構造体を受け取るアンマネージ関数をマネージ関数から呼び出す方法を示します。  マネージ関数は、構造体のインスタンスを作成し、[ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) キーワードの代わりに新しいキーワードを使用して埋め込みポインターを初期化します。  これにより、ネイティブ ヒープ上にメモリが割り当てられるため、ガベージ コレクションを抑制するために配列を固定する必要がなくなります。  ただし、メモリ リークを回避するためにメモリを明示的に削除する必要があります。  
  
```  
// marshal_embedded_pointer.cpp  
// compile with: /clr  
#include <iostream>  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
// unmanaged struct  
struct ListStruct {  
   int count;  
   double* item;  
};  
  
#pragma unmanaged  
  
void UnmanagedTakesListStruct(ListStruct list) {  
   printf_s("[unmanaged] count = %d\n", list.count);  
   for (int i=0; i<list.count; i++)  
      printf_s("array[%d] = %f\n", i, list.item[i]);  
}  
  
#pragma managed  
  
int main() {  
   ListStruct list;  
   list.count = 10;  
   list.item = new double[list.count];  
  
   Console::WriteLine("[managed] count = {0}", list.count);  
   Random^ r = gcnew Random(0);  
   for (int i=0; i<list.count; i++) {  
      list.item[i] = r->NextDouble() * 100.0;  
      Console::WriteLine("array[{0}] = {1}", i, list.item[i]);  
   }  
  
   UnmanagedTakesListStruct( list );  
   delete list.item;  
}  
```  
  
  **\[managed\] count \= 10**  
**array\[0\] \= 72.624326996796**  
**array\[1\] \= 81.7325359590969**  
**array\[2\] \= 76.8022689394663**  
**array\[3\] \= 55.8161191436537**  
**array\[4\] \= 20.6033154021033**  
**array\[5\] \= 55.8884794618415**  
**array\[6\] \= 90.6027066011926**  
**array\[7\] \= 44.2177873310716**  
**array\[8\] \= 97.754975314138**  
**array\[9\] \= 27.370445768987**  
**\[unmanaged\] count \= 10**  
**array\[0\] \= 72.624327**  
**array\[1\] \= 81.732536**  
**array\[2\] \= 76.802269**  
**array\[3\] \= 55.816119**  
**array\[4\] \= 20.603315**  
**array\[5\] \= 55.888479**  
**array\[6\] \= 90.602707**  
**array\[7\] \= 44.217787**  
**array\[8\] \= 97.754975**  
**array\[9\] \= 27.370446**   
## 参照  
 [C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)