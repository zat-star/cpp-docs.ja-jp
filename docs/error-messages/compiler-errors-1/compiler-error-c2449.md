---
title: "コンパイラ エラー C2449 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2449
dev_langs: C++
helpviewer_keywords: C2449
ms.assetid: 544bf0b6-daa0-40e8-9f21-8e583d472a2d
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2736462f86446ada205d43afdbde63374e689254
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2449"></a>コンパイラ エラー C2449
見つかった ' {' ファイル スコープ (関数のヘッダーがありません)。  
  
 始め中かっこは、ファイル スコープで発生します。  
  
 このエラーは、関数のヘッダーと、関数定義の中かっこの間のセミコロンで発生することができます。  
  
 次の例では、C2499 が生成されます。  
  
```  
// C2449.c  
// compile with: /c  
void __stdcall func(void) {}   // OK  
void __stdcall func(void);  // extra semicolon on this line  
{                         // C2449 detected here  
```