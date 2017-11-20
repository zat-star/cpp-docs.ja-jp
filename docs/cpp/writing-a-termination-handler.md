---
title: "終了ハンドラーの記述 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- structured exception handling [C++], termination handlers
- exceptions [C++], terminating
- termination handlers [C++], writing
- handlers [C++]
- handlers [C++], termination
- termination handlers
- exception handling [C++], termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 52aa1f8f-f8dd-44b8-be94-5e2fc88d44fb
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a4a90c28f9bb2a681e88463dfd6bd9d3ff0a1d99
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="writing-a-termination-handler"></a>終了ハンドラーの記述
例外ハンドラーとは異なり、終了ハンドラーは、コードの保護されたブロックが正常に終了したかどうかに関係なく、常に実行されます。 終了ハンドラーの唯一の目的は、コードのセクションの実行がどのように終了したかに関係なく、メモリ、ハンドル、ファイルなどのリソースが適切に閉じられるようにすることです。  
  
 終了ハンドラーは、try-finally ステートメントを使用します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [Try-finally ステートメント](../cpp/try-finally-statement.md)  
  
-   [リソースのクリーンアップ](../cpp/cleaning-up-resources.md)  
  
-   [例外処理のアクションのタイミング](../cpp/timing-of-exception-handling-a-summary.md)  
  
-   [終了ハンドラーに関する制約](../cpp/restrictions-on-termination-handlers.md)  
  
## <a name="see-also"></a>関連項目  
 [構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)