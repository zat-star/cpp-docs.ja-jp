---
title: "コンパイラの警告 (レベル 1) C4731 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4731
dev_langs: C++
helpviewer_keywords: C4731
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9d8c59a22166c3f4f44db3bea43e241a2199009d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4731"></a>コンパイラの警告 (レベル 1) C4731
'pointer': フレーム ポインター レジスタ 'register' インライン アセンブラー コードによって変更されました。  
  
 フレーム ポインター レジスタが変更されました。 保存して、インライン アセンブリ ブロックまたはフレーム変数 (ローカルまたはによって変更されたレジスタのパラメーター) に登録を復元する必要がありますか、コードが正しく動作しない可能性があります。  
  
 次の例では、C4731 が生成されます。  
  
```  
// C4731.cpp  
// compile with: /W1 /LD  
// processor: x86  
// C4731 expected  
void bad(int p) {  
   __asm  
   {  
      mov ebp, 1  
   }  
  
   if (p == 1)  
   {  
      // ...  
   }  
}  
```  
  
 EBP が (FPO は許可されていません) フレーム ポインターであり変更しています。 ときに`p`後は、参照、に対する相対参照されている`EBP`です。 しかし、`EBP`が、コードで上書きされているため、プログラムが正しく動作しないもエラーの可能性があります。