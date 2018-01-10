---
title: "コンパイラ エラー C2812 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2812
dev_langs: C++
helpviewer_keywords: C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 12ab4a753ad2098dfa4c3bccb2190c18bcc2fafb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2812"></a>コンパイラ エラー C2812
\#インポートは/clr でサポートされていません:/clr:pure および/clr:safe  
  
 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で使用されていません。  
  
 [#import ディレクティブ](../../preprocessor/hash-import-directive-cpp.md)でサポートされていない**/clr: 純粋な**と**/clr:safe**ため`#import`ネイティブ コンパイラのサポート ライブラリの使用が必要です。  
  
## <a name="example"></a>例  
 次の例では、C2812 を生成します。  
  
```  
// C2812.cpp  
// compile with: /clr:pure /c  
#import "importlib.tlb"   // C2812  
```