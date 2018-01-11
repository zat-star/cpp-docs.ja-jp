---
title: "コンパイラ エラー C2410 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2410
dev_langs: C++
helpviewer_keywords: C2410
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3cd5dfa7b33f5af5c57f6479170a7a56df39a0e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2410"></a>コンパイラ エラー C2410
'identifier': 'context' であいまいなメンバー名  
  
 識別子は、1 つ以上の構造体または共用体には、このコンテキストのメンバーです。  
  
 エラーが発生したオペランドを構造体または共用体の指定子を使用します。 構造体または共用体の指定子は型の識別子`struct`または`union`(、`typedef`名または構造体または共用体が参照されていると同じ型の変数)。 指定子は、オペランドを使用する最初のメンバー選択演算子 (.) の左オペランドである必要があります。