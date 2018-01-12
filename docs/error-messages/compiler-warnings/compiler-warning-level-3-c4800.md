---
title: "コンパイラの警告 (レベル 3) C4800 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4800
dev_langs: C++
helpviewer_keywords: C4800
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 687b0dab996bfbfe2ce30d65b86196383c02b914
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4800"></a>コンパイラの警告 (レベル 3) C4800  
  
> '*型*': 値を強制的にブール値 'true' または 'false' (パフォーマンスの警告)  
  
値ができない場合、この警告が生成された`bool`が割り当てられているか、型に強制型変換`bool`です。 通常、このメッセージは割り当てることによって発生`int`変数を`bool`変数を`int`変数には値のみが含まれています**true**と**false**、れる可能性があります型として再宣言`bool`です。 型を使用する式を書き直すことができない場合`bool`、追加することができますし、"`!=0`"式の型を提供するには、式を`bool`です。 式を型にキャスト`bool`デザインでは、警告は無効にします。  
  
この警告は、Visual Studio 2017 で不要になった生成されます。  
  
## <a name="example"></a>例
  
 次の例では、C4800 を生成し、その修正方法を示しています。  
  
```cpp  
// C4800.cpp  
// compile with: /W3  
int main() {  
   int i = 0;  
  
   // To fix, instead try:  
   // bool i = 0;  
  
   bool j = i;   // C4800  
   j++;  
}  
```