---
title: "コンパイラの警告 (レベル 1) C4953 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4953
dev_langs: C++
helpviewer_keywords: C4953
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 807e091838db20fdcf66a74fe3050cf192fab1e3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4953"></a>コンパイラの警告 (レベル 1) C4953
プロファイル データが収集されてから、インライン 'function' が編集されました。プロファイル データは使用されません。  
  
 [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)の使用時に、 `/LTCG:PGINSTRUMENT` の後で再コンパイルされた入力モジュールが検出されました。このモジュールには、編集された関数 (***function***) があります。既存のテストの実行では、その関数がインライン展開の候補として識別されました。 ただし、モジュールの再コンパイルの結果、関数はインライン展開の候補ではなくなります。  
  
 これは、情報提供の警告です。 この警告を解決するには、 `/LTCG:PGINSTRUMENT`を実行してすべてのテストを再実行し、 `/LTCG:PGOPTIMIZE`を実行します。  
  
 `/LTCG:PGOPTIMIZE` が使用されていた場合、この警告はエラーに置き換わります。