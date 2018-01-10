---
title: "ML の致命的でないエラー A2008 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2008
dev_langs: C++
helpviewer_keywords: A2008
ms.assetid: ca24157f-c88a-4678-ae06-3bc3cd956001
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a268fd3f82b96698d8e200486c2091cabfad95ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ml-nonfatal-error-a2008"></a>ML の致命的でないエラー A2008
**構文エラー:**  
  
 現在の場所にトークンには、構文エラーが発生しました。  
  
 次のいずれかが発生した可能性があります。  
  
-   ドット プレフィックスを追加またはディレクティブから省略するとします。  
  
-   予約語 (など**C**または**サイズ**) 識別子として使用されました。  
  
-   現在のプロセッサまたはコプロセッサの選択を利用できなかった命令が使用されました。  
  
-   比較の実行時演算子 (など`==`)、関係演算子ではなく条件付きの assembly ステートメントで使用されていた (など[EQ](../../assembler/masm/operator-eq.md))。  
  
-   命令またはディレクティブが少なすぎますオペランドが指定されました。  
  
-   旧式のディレクティブが使用されました。  
  
## <a name="see-also"></a>参照  
 [ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)