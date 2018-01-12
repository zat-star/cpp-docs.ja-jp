---
title: "コンパイラ エラー C2491 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2491
dev_langs: C++
helpviewer_keywords: C2491
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fec3aba1430849b68076328db8c1084a2bca3221
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2491"></a>コンパイラ エラー C2491
'識別子': dllimport 関数の定義は許可されていません。  
  
 データ、静的データ メンバー、および関数は `dllimport` として宣言できますが、`dllimport` として定義することはできません。  
  
 この問題を解決するには、関数の定義から `__declspec(dllimport)` 指定子を削除します。  
  
 次の例では警告 C2491 が生成されます。  
  
```  
// C2491.cpp  
// compile with: /c  
// function definition  
void __declspec(dllimport) funcB() {}   // C2491  
  
// function declaration  
void __declspec(dllimport) funcB();   // OK  
```