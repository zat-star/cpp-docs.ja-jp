---
title: "コンパイラ エラー C2530 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2530
dev_langs:
- C++
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f9ea1b462f2e0b141bdc624d77f548f19c4b71a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2530"></a>コンパイラ エラー C2530
'identifier': 参照を初期化する必要があります  
  
 既に宣言されていない限り、宣言されているときに参照を初期化する必要があります。  
  
-   キーワードを使用して[extern](../../cpp/using-extern-to-specify-linkage.md)です。  
  
-   クラス、構造体、または共用体のメンバーとして (および、コンス トラクターで初期化されます)。  
  
-   関数宣言または定義でパラメーター。  
  
-   関数の戻り値の型。  
  
 次の例では、C2530 が生成されます。  
  
```  
// C2530.cpp  
int main() {  
   int i = 0;  
   int &j;   // C2530  
   int &k = i;   // OK  
}  
```