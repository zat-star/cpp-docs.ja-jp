---
title: "リソース コンパイラ エラー RC2151 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC2151
dev_langs:
- C++
helpviewer_keywords:
- RC2151
ms.assetid: 3c47e535-c78d-4338-aab9-9b47e2c34728
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
ms.openlocfilehash: b5893d4622fb36d0a5dfb54a4003ddf178de05d1
ms.lasthandoff: 02/24/2017

---
# <a name="resource-compiler-error-rc2151"></a>リソース コンパイラ エラー RC2151
文字列定数を再利用することはできません。  
  
 2 回の同じ値を使用している、 **STRINGTABLE**ステートメントです。 10 進数と&16; 進数の値を誤ってを混在させてされていないことを確認します。  
  
 内の各 ID、 **STRINGTABLE**で一意である必要があります。 効率を最大使用 16 の倍数で始まる連続した定数。
