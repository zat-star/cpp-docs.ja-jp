---
title: "コンパイラ エラー C2812 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2812
dev_langs:
- C++
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 358d0d3a5c7f0129d74be70c3309337542807d1d
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2812"></a>コンパイラ エラー C2812
\#/clr でのインポートはサポートされていません: 純粋なと/clr:safe  
  
 **/Clr: 純粋な**と**/clr:safe**コンパイラ オプションは、Visual Studio 2015 で廃止されました。  
  
 [#import ディレクティブ](../../preprocessor/hash-import-directive-cpp.md)はサポートされていない**/clr: 純粋な**と**/clr:safe**ため`#import`ネイティブ コンパイラ サポート ライブラリの使用を要求します。  
  
## <a name="example"></a>例  
 次の例では、c2812 エラーを生成します。  
  
```  
// C2812.cpp  
// compile with: /clr:pure /c  
#import "importlib.tlb"   // C2812  
```
