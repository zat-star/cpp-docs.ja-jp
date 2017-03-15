---
title: "リソース コンパイラ エラー RC2001 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC2001
dev_langs:
- C++
helpviewer_keywords:
- RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
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
ms.openlocfilehash: ba9e855e61af80d29a682738a3f04377f49b6bdf
ms.lasthandoff: 02/24/2017

---
# <a name="resource-compiler-error-rc2001"></a>リソース コンパイラ エラー RC2001
定数が&2; 行目に続いています。  
  
 文字列定数が続行されましたなし&2; 行目に、円記号 (**\\**) または終了と開始の二重引用符 (**"**)。  
  
 ソース ファイル内の&2; つの行にある文字列定数を解除するには、次のいずれかの操作を行います。  
  
-   行連結文字の円記号では、最初の行を終了します。  
  
-   二重引用符では、最初の行の文字列を閉じ、もう&1; つ引用符に次の行に文字列を開きます。  
  
 \N、文字列定数に改行文字を埋め込むためのエスケープ シーケンスでは、最初の行を終了するのに十分ではありません。
