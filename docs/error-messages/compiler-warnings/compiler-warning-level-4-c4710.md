---
title: "コンパイラの警告 (レベル 4) C4710 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4710
dev_langs:
- C++
helpviewer_keywords:
- C4710
ms.assetid: 76381ec7-3fc1-4bee-9a0a-c2c8307b92e2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e0464d924c21a029a97a8f03d30f88127f3aea6a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4710"></a>コンパイラの警告 (レベル 4) C4710
'function': 関数のインライン関数ではありません  
  
 指定された関数がインライン展開を選択されましたが、コンパイラが実行されなかった、インライン展開されます。  
  
 コンパイラの裁量により、インライン展開が実行されます。 **インライン**キーワードなど、**登録**キーワードは、コンパイラのヒントとして使用します。 コンパイラでは、ヒューリスティックを使用して、インライン、速度にコンパイルするときに、コードを高速化する特定の関数が必要がありますか場合は領域にコンパイルするときは、コードを小さく、特定の関数をインラインにする必要がありますかを確認します。 コンパイラでは、領域用にコンパイルするときに、だけがインライン展開が非常に小規模関数には。  
  
 場合によっては、コンパイラはインライン展開されない特定の関数機械的上の理由からします。 参照してください[C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md)一連の理由により、コンパイラがインライン関数ではない可能性があります。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。