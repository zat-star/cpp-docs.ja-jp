---
title: "コンパイラ エラー C2821 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2821
dev_langs: C++
helpviewer_keywords: C2821
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 842fa67c785173e658742e2b76a0957ded124515
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2821"></a>コンパイラ エラー C2821
'operator new' への最初の仮パラメーターは 'unsigned int' である必要があります。  
  
最初の正式なパラメーター、 [new 演算子](../../standard-library/new-operators.md#op_new)unsigned にする必要があります`int`です。  
  
## <a name="example"></a>例  
 次の例では、C2821 が生成されます。  
  
```cpp  
// C2821.cpp  
// compile with: /c  
void * operator new( /* unsigned int,*/ void * );   // C2821  
void * operator new( unsigned int, void * );  
```