---
title: "コンパイラの警告 (レベル 1) C4036 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4036
dev_langs:
- C++
helpviewer_keywords:
- C4036
ms.assetid: f0b15359-4d62-48ec-8cb1-a7b36587a47f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c266e5148b908b6b3ecbc18ef6d34461767472b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4036"></a>コンパイラの警告 (レベル 1) C4036
実パラメーターとして渡される 'type' に型指定がありません  
  
 実パラメーターとして使用される構造体、共用体、列挙型、またはクラスの型名が指定されていません。 コンパイラは、 [/Zg](../../build/reference/zg-generate-function-prototypes.md) を使用して関数プロトタイプを生成するとこの警告を発行し、生成されたプロトタイプの仮パラメーターをコメントアウトします。  
  
 この警告を解決するには、型名を指定します。  
  
## <a name="example"></a>例  
 次の例では C4036 が生成されます。  
  
```  
// C4036.c  
// compile with: /Zg /W1  
// D9035 expected  
typedef struct { int i; } T;  
void f(T* t) {}   // C4036  
  
// OK  
typedef struct MyStruct { int i; } T2;  
void f2(T2 * t) {}  
```