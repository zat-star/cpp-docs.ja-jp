---
title: "コンパイラ エラー C2505 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2505
dev_langs: C++
helpviewer_keywords: C2505
ms.assetid: b19f5c53-399d-425e-90db-fe3ca9b40858
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e703a5f36a5edd5febbcfaf4b75394bbbb28ee4d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2505"></a>コンパイラ エラー C2505
'symbol': '__declspec(modifer)' は、グローバル オブジェクトまたは静的データ メンバーの宣言または定義にのみ適用できます  
  
 A`__declspec`グローバル スコープでのみ使用するように設計された修飾子は関数で使用されました。  
  
 詳細については、「 [appdomain](../../cpp/appdomain.md) 」および「 [process](../../cpp/process.md)」を参照してください。  
  
 次の例では、C2505 が生成されます。  
  
```  
// C2505.cpp  
// compile with: /clr  
  
// OK  
__declspec(process) int ii;  
__declspec(appdomain) int jj;  
  
int main() {  
   __declspec(process) int i;   // C2505  
   __declspec(appdomain) int j;   // C2505  
}  
```