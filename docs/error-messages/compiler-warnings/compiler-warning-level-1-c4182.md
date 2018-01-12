---
title: "コンパイラの警告 (レベル 1) C4182 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4182
dev_langs: C++
helpviewer_keywords: C4182
ms.assetid: 8970f3c6-e2dd-407e-b2ec-964360eb8b43
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3ef78cebafcb07977611f92ad9f49a3d5b2c3dde
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4182"></a>コンパイラの警告 (レベル 1) C4182
\#入れ子のレベルは 'number' です無限再帰の可能性  
  
 コンパイラがヒープ上の領域を使い切りました。入れ子になっているインクルード ファイルの数が原因です。 インクルード ファイルは、別のインクルード ファイルに含められると入れ子になります。  
  
 このメッセージは情報目的で、エラー [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md)に先だって表示されます。