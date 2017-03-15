---
title: "コンパイラの警告 (レベル 1) C4953 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4953
dev_langs:
- C++
helpviewer_keywords:
- C4953
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: be8e32bd07da47d79e974d979eb19466c5b19416
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4953"></a>コンパイラの警告 (レベル 1) C4953
プロファイル データが収集されてから、インライン 'function' が編集されました。プロファイル データは使用されません。  
  
 使用する場合[/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)、後に再コンパイルされた入力モジュールが検出されました`/LTCG:PGINSTRUMENT`には、関数が (***関数***) が編集されるの候補として関数を識別する既存のテストが実行されるインライン展開されます。 ただし、モジュールの再コンパイルの結果、関数はインライン展開の候補ではなくなります。  
  
 これは、情報提供の警告です。 この警告を解決するには、 `/LTCG:PGINSTRUMENT`を実行してすべてのテストを再実行し、 `/LTCG:PGOPTIMIZE`を実行します。  
  
 `/LTCG:PGOPTIMIZE` が使用されていた場合、この警告はエラーに置き換わります。
