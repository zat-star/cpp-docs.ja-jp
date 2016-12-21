---
title: "方法: C++ Interop を使用して構造体をマーシャリングする | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "C++ 相互運用機能, 構造体"
  - "データ マーシャリング [C++], 構造体"
  - "相互運用 [C++], 構造体"
  - "マーシャリング [C++], 構造体"
  - "構造体 [C++], マーシャリング"
ms.assetid: c2080200-f983-4d6e-a557-cd870f060a54
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: C++ Interop を使用して構造体をマーシャリングする
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、Visual C\+\+ の相互運用性の 1 つのファセットについて説明します。  詳細については、「[C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)」を参照してください。  
  
 次のコード例では、[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md) の \#pragma ディレクティブを使用してマネージ関数とアンマネージ関数を同じファイル内で実装していますが、これらの関数は、別個のファイルに定義された場合も同じように相互運用できます。  アンマネージ関数のみを含むファイルは、[\/clr \(共通言語ランタイムのコンパイル\)](../build/reference/clr-common-language-runtime-compilation.md) でコンパイルする必要はありません。  
  
## 使用例  
 マネージ関数からアンマネージ関数に、値渡しおよび参照渡しの両方で構造体を渡す方法を次の例に示します。  この例で示す構造体には単純な組み込みデータ型しか含まれていないので \(「[Blittable 型と非 Blittable 型](../Topic/Blittable%20and%20Non-Blittable%20Types.md)」を参照\)、特別なマーシャリングは必要ありません。  ポインターを含む構造体のような非 blittable 型の構造体をマーシャリングするには、「[方法: C\+\+ Interop を使用して埋め込みポインターをマーシャリングする](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)」を参照してください。  
  
```  
// PassStruct1.cpp  
// compile with: /clr  
  
#include <stdio.h>  
#include <math.h>  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
struct Location {  
   int x;  
   int y;  
};  
  
double GetDistance(Location loc1, Location loc2) {  
   printf_s("[unmanaged] loc1(%d,%d)", loc1.x, loc1.y);  
   printf_s(" loc2(%d,%d)\n", loc2.x, loc2.y);  
  
   double h = loc1.x - loc2.x;  
   double v = loc1.y = loc2.y;  
   double dist = sqrt( pow(h,2) + pow(v,2) );  
  
   return dist;  
}  
  
void InitLocation(Location* lp) {  
   printf_s("[unmanaged] Initializing location...\n");  
   lp->x = 50;  
   lp->y = 50;  
}  
  
#pragma managed  
  
int main() {  
   Location loc1;  
   loc1.x = 0;  
   loc1.y = 0;  
  
   Location loc2;  
   loc2.x = 100;  
   loc2.y = 100;  
  
   double dist = GetDistance(loc1, loc2);  
   Console::WriteLine("[managed] distance = {0}", dist);  
  
   Location loc3;  
   InitLocation(&loc3);  
   Console::WriteLine("[managed] x={0} y={1}", loc3.x, loc3.y);  
}  
```  
  
## 使用例  
 アンマネージ関数からマネージ関数に、値渡しおよび参照渡しの両方で構造体を渡す方法を次の例に示します。  この例で示す構造体には単純な組み込みデータ型しか含まれていないので \(「[Blittable 型と非 Blittable 型](../Topic/Blittable%20and%20Non-Blittable%20Types.md)」を参照\)、特別なマーシャリングは必要ありません。  ポインターを含む構造体のような非 blittable 型の構造体をマーシャリングするには、「[方法: C\+\+ Interop を使用して埋め込みポインターをマーシャリングする](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)」を参照してください。  
  
```  
// PassStruct2.cpp  
// compile with: /clr  
#include <stdio.h>  
#include <math.h>  
using namespace System;  
  
// native structure definition  
struct Location {  
   int x;  
   int y;  
};  
  
#pragma managed  
  
double GetDistance(Location loc1, Location loc2) {  
   Console::Write("[managed] got loc1({0},{1})", loc1.x, loc1.y);  
   Console::WriteLine(" loc2({0},{1})", loc2.x, loc2.y);  
  
   double h = loc1.x - loc2.x;  
   double v = loc1.y = loc2.y;  
   double dist = sqrt( pow(h,2) + pow(v,2) );  
  
   return dist;  
}  
  
void InitLocation(Location* lp) {  
   Console::WriteLine("[managed] Initializing location...");  
   lp->x = 50;  
   lp->y = 50;  
}  
  
#pragma unmanaged  
  
int UnmanagedFunc() {  
   Location loc1;  
   loc1.x = 0;  
   loc1.y = 0;  
  
   Location loc2;  
   loc2.x = 100;  
   loc2.y = 100;  
  
   printf_s("(unmanaged) loc1=(%d,%d)", loc1.x, loc1.y);  
   printf_s(" loc2=(%d,%d)\n", loc2.x, loc2.y);  
  
   double dist = GetDistance(loc1, loc2);  
   printf_s("[unmanaged] distance = %f\n", dist);  
  
   Location loc3;  
   InitLocation(&loc3);  
   printf_s("[unmanaged] got x=%d y=%d\n", loc3.x, loc3.y);  
  
    return 0;  
}  
  
#pragma managed  
  
int main() {  
   UnmanagedFunc();  
}  
```  
  
## 参照  
 [C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)