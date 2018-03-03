---
title: "リンカー ツールの警告 LNK4217 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4217
dev_langs:
- C++
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 09c984d7675c73bdf225bae7d3014f81153d20e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4217"></a>リンカー ツールの警告 LNK4217
ローカルに定義されたシンボル 'symbol' 関数 'function' でインポート  
  
 [_declspec (dllimport)](../../cpp/dllexport-dllimport.md)シンボルがローカルに定義されている場合でも、シンボルが指定されました。 削除、`__declspec`この警告を解決するのには修飾子です。  
  
 `symbol`イメージ内で定義されているシンボルの名前です。 `function`シンボルをインポートする関数です。  
  
 オプションを使用してコンパイルするときに、この警告は表示されません[/clr](../../build/reference/clr-common-language-runtime-compilation.md)です。  
  
 LNK4217 は、代わりに、最初のモジュールのインポート ライブラリと 2 番目のモジュールをコンパイルするときに同時に、2 つのモジュールをリンクしようとする場合にも発生することができます。  
  
```  
// LNK4217.cpp  
// compile with: /LD  
#include "windows.h"  
__declspec(dllexport) void func(unsigned short*) {}  
```  
  
 この場合、次のようになります。  
  
```  
// LNK4217b.cpp  
// compile with: /c  
#include "windows.h"  
__declspec(dllexport) void func(unsigned short*) {}  
```  
  
 これら 2 つのモジュールをリンクしようとして、LNK4217 が発生、2 つ目のサンプルを解決するのには、最初のサンプルのインポート ライブラリをコンパイルします。