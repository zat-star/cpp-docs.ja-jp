---
title: "コンパイラの警告 (レベル 1) C4952 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4952
dev_langs:
- C++
helpviewer_keywords:
- C4952
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: fa48ab2f0e7a2a9d7675af5d2e88aa56b100f022
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4952"></a>コンパイラの警告 (レベル 1) C4952
'function': プログラム データベース 'pgd_file' にプロファイル データが見つかりません。  
  
 使用する場合[/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)を後に再コンパイルされた入力モジュールが検出されました`/LTCG:PGINSTRUMENT`新しい関数が存在し、(***関数***) に存在します。  
  
 これは、情報提供の警告です。 この警告を解決するには、 `/LTCG:PGINSTRUMENT`を実行してすべてのテストを再実行し、 `/LTCG:PGOPTIMIZE`を実行します。  
  
 `/LTCG:PGOPTIMIZE` が使用されていた場合、この警告はエラーに置き換わります。
