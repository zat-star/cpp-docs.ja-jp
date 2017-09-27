---
title: "noinline |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- noinline
- noinline_cpp
dev_langs:
- C++
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 2ba1e7f6563b480cadc171bd6cea6e5fb4cb9839
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

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


