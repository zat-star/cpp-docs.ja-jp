---
title: "コンパイラ エラー C2603 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2603
dev_langs:
- C++
helpviewer_keywords:
- C2603
ms.assetid: 9ca520d0-f082-4b65-933d-17c3bcf8b02c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c06c5747a3d785242e8b926fe6e1eaa251a2d8b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2603"></a>コンパイラ エラー C2603  
  
> '*関数*': 関数内のコンス トラクター/デストラクターにブロック スコープスタティック オブジェクトが多すぎます  
  
Visual Studio 2015 では、前に、Visual C コンパイラのバージョンの場合や、 [/Zc:threadSafeInit-](../../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md)コンパイラ オプションを指定すると、31 外部から参照できるインライン関数では、静的オブジェクトの数の制限があります.  
  
この問題を解決するより新しいバージョンの Visual C コンパイラ ツールセットを採用するか、可能な場合は、/Zc:threadSafeInit-コンパイラ オプションを削除お勧めします。 これが可能でない場合は、静的オブジェクトの組み合わせを検討します。 オブジェクトが同じ型の場合、その型の 1 つの静的な配列の使用を検討し、必要に応じて個々 のメンバーを参照します。
  
## <a name="example"></a>例  
  
次のコードでは、C2603 を生成し、その修正方法を示しています。  
  
```cpp  
// C2603.cpp  
// Compile by using: cl /W4 /c /Zc:threadSafeInit- C2603.cpp
struct C { C() {} };  
extern inline void f1() {  
    static C C01, C02, C03, C04, C05, C06, C07, C08, C09, C10;
    static C C11, C12, C13, C14, C15, C16, C17, C18, C19, C20;
    static C C21, C22, C23, C24, C25, C26, C27, C28, C29, C30, C31;  
    static C C32;   // C2603 Comment this line out to avoid error  
}  
```
