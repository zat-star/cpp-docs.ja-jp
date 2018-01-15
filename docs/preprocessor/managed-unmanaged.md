---
title: "マネージ、アンマネージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.unmanaged
- managed_CPP
- unmanaged_CPP
- vc-pragma.managed
dev_langs: C++
helpviewer_keywords:
- managed pragma
- pragmas, unmanaged
- pragmas, managed
- unmanaged pragma
ms.assetid: f072ddcc-e1ec-408a-8ce1-326ddb60e4a4
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2d8e2b50f7d505a4e262559b6cb69b0bab81ffcd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="managed-unmanaged"></a>マネージ、アンマネージ
関数をマネージまたはアンマネージとしてコンパイルするために関数レベルの制御を有効にします。  
  
## <a name="syntax"></a>構文  
  
```  
  
      #pragma managed  
#pragma unmanaged  
#pragma managed([push,] on | off)  
#pragma managed(pop)  
```  
  
## <a name="remarks"></a>コメント  
 [/Clr](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションは、モジュール レベルの制御関数をマネージまたはアンマネージとしてコンパイルします。  
  
 アンマネージ関数は、ネイティブ プラットフォーム用にコンパイルされ、プログラムのその部分の実行は、共通言語ランタイムによってネイティブ プラットフォームに渡されます。  
  
 既定では管理対象として、関数がコンパイルされたときに**/clr**を使用します。  
  
 これらのプラグマを適用するときは次のようにします。  
  
-   関数の前にあり関数本体内にはないプラグマを追加します。  
  
-   `#include` ステートメントの後にプラグマを追加します。 `#include` ステートメントの前でこれらのプラグマを使用しないでください。  
  
 コンパイラは無視、`managed`と`unmanaged`プラグマ場合**/clr**コンパイルでは使用されません。  
  
 テンプレート関数がインスタンス化されるとき、テンプレートの定義時のプラグマの状態により、マネージかアンマネージかが決まります。  
  
 詳細については、次を参照してください。[混在アセンブリの初期化](../dotnet/initialization-of-mixed-assemblies.md)です。  
  
## <a name="example"></a>例  
  
```cpp  
// pragma_directives_managed_unmanaged.cpp  
// compile with: /clr  
#include <stdio.h>  
  
// func1 is managed  
void func1() {  
   System::Console::WriteLine("In managed function.");  
}  
  
// #pragma unmanaged  
// push managed state on to stack and set unmanaged state  
#pragma managed(push, off)  
  
// func2 is unmanaged  
void func2() {  
   printf("In unmanaged function.\n");  
}  
  
// #pragma managed  
#pragma managed(pop)  
  
// main is managed  
int main() {  
   func1();  
   func2();  
}  
```  
  
```Output  
In managed function.  
In unmanaged function.  
```  
  
## <a name="see-also"></a>参照  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)