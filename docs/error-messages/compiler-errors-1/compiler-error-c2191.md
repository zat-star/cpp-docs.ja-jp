---
title: "コンパイラ エラー C2191 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2191
dev_langs: C++
helpviewer_keywords: C2191
ms.assetid: 051b8350-e5de-4f51-ab6e-96d32366bcef
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 32dccf8bbda13911dbf21b319f1a4fb375ddd1df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2191"></a>コンパイラ エラー C2191
最初よりも長い 2 番目のパラメーター リスト  
  
 C の関数は、長いパラメーター リストで 2 番目の時間を宣言されました。 C では、オーバー ロードされた関数はサポートされません。  
  
## <a name="example"></a>例  
 次の例では、C2191 が生成されます。  
  
```  
// C2191.c  
// compile with: /Za /c  
void func( int );  
void func( int, float );   // C2191 different parameter list  
void func2( int, float );   // OK  
```