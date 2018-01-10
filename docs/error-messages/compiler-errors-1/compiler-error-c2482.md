---
title: "コンパイラ エラー C2482 |Microsoft ドキュメント"
ms.custom: 
ms.date: 09/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2482
dev_langs: C++
helpviewer_keywords: C2482
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c4a5d081e7a19f09f10e40e3799f724f44b295fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2482"></a>コンパイラ エラー C2482

>'*識別子*': 'thread' データが許可されていませんの動的な初期化

このエラー メッセージは、Visual Studio 2015 およびそれ以降のバージョンで廃止されています。 以前のバージョンでは変数宣言を使用して、`thread`属性は、実行時の評価が必要な式で初期化できません。 静的な式が初期化に必要な`thread`データ。

## <a name="example"></a>例

次の例では、Visual Studio 2013 以前のバージョンで C2482 が生成されます。

```cpp
// C2482.cpp
// compile with: /c
#define Thread __declspec( thread )
Thread int tls_i = tls_i;   // C2482

int j = j;   // OK in C++; C error
Thread int tls_i = sizeof( tls_i );   // Okay in C and C++
```
