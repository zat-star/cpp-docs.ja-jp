---
title: "例外処理のタイミング: 概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- sequence
- sequence, of handlers
- exception handling, timing
- SETJMPEX.H
- termination handlers, timing
- SETJMP.H
- handlers, order of exception
- structured exception handling, timing
ms.assetid: 5d1da546-73fd-4673-aa1a-7ac0f776c420
caps.latest.revision: 6
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
ms.openlocfilehash: 0ba1075095381229667c7164aa7de7f3e4537486
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="timing-of-exception-handling-a-summary"></a>例外処理のタイミング: 概要
終了ハンドラーは、`__try` ステートメント ブロックがどのように終了された場合も常に実行されます。 終了の原因としては、`__try` ブロックからのジャンプ、制御がブロックの外に移動する `longjmp` ステートメント、例外処理によるスタックのアンワインドなどが考えられます。  
  
> [!NOTE]
>  Visual C++ は、`setjmp` ステートメントと `longjmp` ステートメントの 2 つの形式をサポートします。 高速なバージョンは終了処理をバイパスしますが、より効率的です。 このバージョンを使用するには、SETJMP.H ファイルをインクルードします。 もう一方のバージョンは、前の段落で説明したような終了処理をサポートします。 このバージョンを使用するには、SETJMPEX.H ファイルをインクルードします。 高速バージョンでパフォーマンスがどの程度向上するかは、ハードウェア構成によって異なります。  
  
 オペレーティング システムは、例外ハンドラー本体を含む他のあらゆるコードを実行する前に、適切な順序ですべての終了ハンドラーを実行します。  
  
 中断の原因が例外の場合、システムは終了対象を決める前に、最初に 1 つ以上の例外ハンドラーのフィルター部分を実行する必要があります。 イベントの順序は次のとおりです。  
  
1.  例外が発生します。  
  
2.  システムは、アクティブな例外ハンドラーの階層を参照し、最も優先順位が高いハンドラーのフィルターを実行します。これは、ブロックと関数呼び出しの点から見て、最も後にインストールされ、最も深く入れ子になった例外ハンドラーです。  
  
3.  制御がこのフィルターを通過する (フィルターが 0 を返す) と、制御が通過できないフィルターが見つかるまで処理が続行されます。  
  
4.  このフィルターには、-1 が返された場合、ここで例外が発生した、および終了は行われません、実行が続行されます。  
  
5.  フィルターが 1 を返すと、次のイベントが発生します。  
  
    -   システムは、スタックをアンワインドし、現在実行中のコード (例外が発生した場所) と制御を取得している例外ハンドラーを含むスタック フレームの間のすべてのスタック フレームをクリアします。  
  
    -   スタックがアンワインドされると、スタックの各終了ハンドラーが実行されます。  
  
    -   例外ハンドラー自体が実行されます。  
  
    -   この例外ハンドラーの末尾の後ろのコード行に制御が進みます。  
  
## <a name="see-also"></a>関連項目  
 [終了ハンドラーの記述](../cpp/writing-a-termination-handler.md)   
 [構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
