---
title: "コンパイラ エラー C2483 |Microsoft ドキュメント"
ms.custom: 
ms.date: 09/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2483
dev_langs: C++
helpviewer_keywords: C2483
ms.assetid: 5762b325-914b-442d-a604-e4617ba04038
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 45b0f616f62287f82b35dfdfdc03c445ec529177
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2483"></a>コンパイラ エラー C2483

>'*識別子*': 'thread' コンス トラクターまたはデストラクターを持つオブジェクトを宣言することはできません

このエラー メッセージは、Visual Studio 2015 およびそれ以降のバージョンで廃止されています。 以前のバージョンで宣言された変数、`thread`属性は、コンス トラクターまたは実行時の評価が必要なその他の式で初期化できません。 静的な式が初期化に必要な`thread`データ。

## <a name="example"></a>例

次の例では、Visual Studio 2013 以前のバージョンでのみで C2483 が生成されます。

```cpp
// C2483.cpp
// compile with: /c
__declspec(thread) struct A {
   A(){}
   ~A(){}
} aa;   // C2483 error  

__declspec(thread) struct B {} b;   // OK
```

## <a name="see-also"></a>関連項目

[thread](../../cpp/thread.md)