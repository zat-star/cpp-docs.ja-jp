---
title: "リンカ ツール エラー LNK1306 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1306
dev_langs:
- C++
helpviewer_keywords:
- LNK1306
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 32b6589fa5e4d7dc02ccb9a6c3157c109725b895
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1306"></a>リンカ ツール エラー LNK1306  
  
> DLL エントリ ポイント関数を管理することはできません。ネイティブにコンパイルします。  
  
`DllMain`MSIL にコンパイルすることはできませんこれは、ネイティブにコンパイルする必要があります。  
  
この問題を解決するのには  
  
-   せずエントリ ポイントが含まれているファイルをコンパイル**/clr**です。  
  
-   エントリ ポイントを配置する、`#pragma unmanaged`セクションです。  
  
詳細については次を参照してください:  
  
-   [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [managed、unmanaged](../../preprocessor/managed-unmanaged.md)  
  
-   [混在アセンブリの初期化](../../dotnet/initialization-of-mixed-assemblies.md)  
  
-   [DLL と Visual C++ ランタイム ライブラリの動作](../../build/run-time-library-behavior.md)  
  
## <a name="example"></a>例  
  
次の例では、LNK1306 が生成されます。  
  
```cpp  
// LNK1306.cpp  
// compile with: /clr /link /dll /entry:NewDllMain  
// LNK1306 error expected  
#include <windows.h>  
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {  
   return 1;  
}  
```  
  
この問題を解決するオプションを使用しない、/clr を使用したり、このファイルをコンパイル、`#pragma`この例で示すように、アンマネージのセクションにエントリ ポイントの定義を記述するディレクティブ。  
  
```cpp  
// LNK1306fix.cpp  
// compile with: /clr /link /dll /entry:NewDllMain  
#include <windows.h>  
#pragma managed(push, off)  
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {  
   return 1;  
}  
#pragma managed(pop)  
```  
