---
title: "リンカ ツール エラー LNK1306 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1306"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1306"
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# リンカ ツール エラー LNK1306
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

DLL エントリ ポイント '関数' をマネージにすることはできません。ネイティブにコンパイルしてください。  
  
 DllMain を MSIL にコンパイルできなくなりました。ネイティブにコンパイルする必要があります。  
  
 このエラーを解決するには、次のどちらかの操作を実行します。  
  
-   エントリ ポイントを含むファイルを、**\/clr** を指定しないでコンパイルします。  
  
-   エントリ ポイントを `#pragma unmanaged` セクションに配置します。  
  
-   詳細については、次のトピックを参照してください  
  
-   [\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [マネージ、アンマネージ](../../preprocessor/managed-unmanaged.md)  
  
-   [混在アセンブリの初期化](../Topic/Initialization%20of%20Mixed%20Assemblies.md)  
  
-   [ランタイム ライブラリの動作](../../build/run-time-library-behavior.md)  
  
## 使用例  
 次の例では LNK1306 エラーが生成されます。  
  
```  
// LNK1306.cpp  
// compile with: /clr /link /dll /entry:NewDllMain  
// LNK1306 error expected  
#include <windows.h>  
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {  
   return 1;  
}  
```