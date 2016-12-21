---
title: "リンカー ツールの警告 LNK4217 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4217"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4217"
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカー ツールの警告 LNK4217
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ローカルで定義されたシンボル 'symbol' が関数 'function' にインポートされました。  
  
 シンボルに [\_\_declspec\(dllimport\)](../../cpp/dllexport-dllimport.md) が指定されましたが、そのシンボルはローカルに定義されています。  `__declspec` 修飾子を削除して、この警告を解決してください。  
  
 `symbol` は、イメージ内で定義されているシンボル名です。  `function` は、シンボルをインポートする関数です。  
  
 [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) オプションを使用してコンパイルした場合、この警告は表示されません。  
  
 LNK4217 は、最初のモジュールのインポート ライブラリを使用して 2 番目のモジュールをコンパイルする必要があるにもかかわらず、この 2 つのモジュールへまとめてリンクしようとしたときにも発生します。  
  
```  
// LNK4217.cpp  
// compile with: /LD  
#include "windows.h"  
__declspec(dllexport) void func(unsigned short*) {}  
```  
  
 次に、以下のコードを実行します。  
  
```  
// LNK4217b.cpp  
// compile with: /c  
#include "windows.h"  
__declspec(dllexport) void func(unsigned short*) {}  
```  
  
 この 2 つのモジュールへリンクしようとすると LNK4217 が発生します。これを解決するには、最初のサンプル モジュールのインポート ライブラリを使用して 2 番目のサンプル モジュールをコンパイルします。