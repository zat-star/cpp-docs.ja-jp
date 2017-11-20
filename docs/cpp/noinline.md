---
title: "noinline |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: noinline_cpp
dev_langs: C++
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6b8548f428509c2af45858e1baf927da54ebe8f6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="noinline"></a>noinline
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 **__declspec(noinline)**特定のメンバー関数 (クラスの関数) をインラインにしないことをコンパイラに指示します。  
  
 コードのパフォーマンスにとって大きな意味がなく、重要でなければ、関数をインラインにしない方がよい場合があります。 つまり、関数が小さく、頻繁に呼び出されないと考えられる場合 (エラー条件を処理する関数など)。  
  
 関数が `noinline` とマークされている場合、呼び出し元の関数が小さく、それ自体がコンパイラのインライン展開の候補になることに注意してください。  
  
```  
class X {  
   __declspec(noinline) int mbrfunc() {  
      return 0;   
   }   // will not inline  
};  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_ _declspec](../cpp/declspec.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [inline、__inline、\__forceinline](inline-functions-cpp.md)

