---
title: "致命的なエラー C1509 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1509
dev_langs: C++
helpviewer_keywords: C1509
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 22cb22ea2186b16fd98d2714779b2475c51d15bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1509"></a>致命的なエラー C1509
コンパイラの制限: 関数 'function' の例外ハンドラが多すぎます。 関数を簡略化します。  
  
 コードは、例外ハンドラーの状態 (32,768) 数の内部制限を超えています。  
  
 最も一般的な原因は、関数がクラスのユーザー定義変数および算術演算子の複雑な式が含まれているです。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  一時変数に共通部分式を割り当てることで式を簡略化します。  
  
2.  関数を小さな関数に分割します。