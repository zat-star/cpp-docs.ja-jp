---
title: "ML の致命的でないエラー A2133 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2133
dev_langs: C++
helpviewer_keywords: A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 64619e6e14ce0268516c6c688c9a2bdeb5ea7a11
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ml-nonfatal-error-a2133"></a>ML の致命的でないエラー A2133
**レジスタ値の呼び出しによって上書きされます。**  
  
 レジスタは、プロシージャに引数として渡されたが、コードによって生成[INVOKE](../../assembler/masm/invoke.md)他の引数を渡す、レジスタの内容を破棄します。  
  
 AX、AL、AH、EAX、DX、DL、DH、および EDX レジスタは、アセンブラーによってデータの変換を実行するために使用可能性があります。  
  
 別のレジスタを使用します。  
  
## <a name="see-also"></a>参照  
 [ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)