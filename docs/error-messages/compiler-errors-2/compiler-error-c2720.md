---
title: "コンパイラ エラー C2720 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2720
dev_langs:
- C++
helpviewer_keywords:
- C2720
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cfd1e41ea3b9479f07faa9a1cbf0739bc0b7e8b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2720"></a>コンパイラ エラー C2720  
  
> '*識別子*':'*指定子*' ストレージ クラス指定子のメンバーが無効です  
  
ストレージ クラスは、宣言の外側のクラス メンバーに対して使用することはできません。 このエラーを解決するには、不要な削除[ストレージ クラス](../../cpp/storage-classes-cpp.md)クラス宣言の外側にあるメンバーの定義内の指定子。  
  
## <a name="example"></a>例  
  
次の例では、C2720 を生成し、その修正方法を示しています。  
  
```cpp  
// C2720.cpp  
struct S {  
   static int i;  
};  
static S::i;   // C2720 - remove the unneeded 'static' to fix it  
```