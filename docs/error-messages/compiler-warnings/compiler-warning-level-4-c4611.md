---
title: "コンパイラの警告 (レベル 4) C4611 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4611
dev_langs: C++
helpviewer_keywords: C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3020cf7d115b735141b81e9007ac7fd027ed8674
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4611"></a>コンパイラの警告 (レベル 4) C4611
'function' と C++ オブジェクト デストラクション間の対話は互換性がありません。  
  
 含む関数の一部のプラットフォームで**キャッチ**スコープ外と破棄の C++ オブジェクトのセマンティクスをサポートしていません。  
  
 予期しない動作を回避するのには使用しないでください**キャッチ**をコンス トラクターとデストラクターを持つ関数でします。  
  
 この警告は回だけです。参照してください[pragma 警告](../../preprocessor/warning.md)です。