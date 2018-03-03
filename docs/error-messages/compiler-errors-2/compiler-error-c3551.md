---
title: "コンパイラ エラー C3551 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3551
dev_langs:
- C++
helpviewer_keywords:
- C3551
ms.assetid: c8ee23da-6568-40db-93a6-3ddb7ac47712
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: be8a55c6033150c5f1c4220885b01b4af8b8a6bd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3551"></a>コンパイラ エラー C3551
"遅延指定の戻り値の型が必要です"  
  
 関数の戻り値の型のプレース ホルダーとして `auto` キーワードを使用する場合は、遅延指定の戻り値の型を指定する必要があります。 次の例では、関数 `myFunction` の遅延指定の戻り値の型は、型 `int`の 4 つの要素の配列へのポインターです。  
  
```  
auto myFunction()->int(*)[4];   
```  
  
## <a name="see-also"></a>参照  
 [auto](../../cpp/auto-cpp.md)