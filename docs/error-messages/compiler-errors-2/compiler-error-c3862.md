---
title: "コンパイラ エラー C3862 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3862
dev_langs: C++
helpviewer_keywords: C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: af959252ce5b404d8646ad61e02c5e480b41ed83
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3862"></a>コンパイラ エラー C3862
'function':/clr でアンマネージ関数をコンパイルできません:/clr:pure または/clr:safe  
  
 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で使用されていません。  
  
 使用してコンパイル**/clr: 純粋な**または**/clr:safe**はイメージとネイティブ (アンマネージ) コードを含まない、MSIL のみイメージを生成します。  したがって、使用することはできません、`unmanaged`プラグマ、 **/clr: 純粋な**または**/clr:safe**コンパイルします。  
  
 詳細については、次を参照してください。 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)と[マネージ、アンマネージ](../../preprocessor/managed-unmanaged.md)です。  
  
## <a name="example"></a>例  
 次の例では、C3862 が生成されます。  
  
```  
// C3862.cpp  
// compile with: /clr:pure /c  
#pragma unmanaged  
void f() {}   // C3862  
```