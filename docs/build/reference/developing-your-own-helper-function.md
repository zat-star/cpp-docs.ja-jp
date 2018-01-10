---
title: "独自のヘルパー関数の作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: helper functions
ms.assetid: a845429d-68b1-4e14-aa88-f3f5343bd490
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 76172804cc271a740244d06e791db35d534c69e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="developing-your-own-helper-function"></a>独自のヘルパー関数の作成
DLL またはインポートの名前に基づく特定の処理を実行するルーチンのバージョンを独自に提供することがあります。 これを 2 つの方法はあります。 可能性のある、指定されたコードに基づくのコーディング独自、または以前に詳細な通知フックを使用して指定されたバージョンにフックするだけでします。  
  
 独自のコードします。  
 これは、設定できるので本質的に指定されたコードをガイドラインとして、新しい非常にシンプルです。 もちろん、呼び出し規約に従う必要がありますが、リンカーによって生成されたサンクに返された場合、適切な関数ポインターを返す必要があります。 1 回、コードで非常に希望の呼び出しを満たすか、呼び出しから取得するために実行できます。  
  
 使用して、処理開始通知フック  
 単に通知 dliStartProcessing で既定のヘルパーと同じ値を受信するユーザーが指定した通知用のフック関数への新しいポインターを提供する最も簡単なことが考えられます。 その時点では、フック関数は、実質的に新しいヘルパー関数に、ように正常に返された既定のヘルパーにはそれ以降のすべての既定のヘルパーの処理をバイパスします。  
  
## <a name="see-also"></a>参照  
 [リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)