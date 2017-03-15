---
title: "式エバリュエーター エラー CXX0033 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0033
dev_langs:
- C++
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 3df60f5eed5a5018fd5dade69d10e1302db868f1
ms.lasthandoff: 02/24/2017

---
# <a name="expression-evaluator-error-cxx0033"></a>式エバリュエーター エラー CXX0033
OMF の型情報にエラーがあります  
  
 実行可能ファイルには、デバッグの有効なオブジェクト モジュール形式 (OMF) がありませんでした。  
  
 このエラーは、can0033 と同じものと同じです。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  このバージョンの Visual C リンカーによって実行可能ファイルが作成されませんでした。 LINK.exe の現在のバージョンを使用してオブジェクト コードを再リンクします。  
  
2.  .Exe ファイルが壊れている可能性があります。 再コンパイルし、プログラムを再リンクします。
