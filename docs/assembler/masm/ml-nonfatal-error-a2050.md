---
title: "ML の致命的でないエラー A2050 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2050
dev_langs: C++
helpviewer_keywords: A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a51a90f294afd0347057efb04ab37ce790532ba4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ml-nonfatal-error-a2050"></a>ML の致命的でないエラー A2050
**real または BCD 番号は使用できません。**  
  
 浮動小数点 (実際) の数または binary coded decimal (BCD) 定数が以外に使用したデータの初期化子として。  
  
 次のいずれかが発生しました。  
  
-   実数または BCD は、式で使用されました。  
  
-   以外のディレクティブを初期化するために使用された実数[DWORD](../../assembler/masm/dword.md)、 [QWORD](../../assembler/masm/qword.md)、または[TBYTE](../../assembler/masm/tbyte.md)です。  
  
-   以外のディレクティブを初期化するために使用された BCD`TBYTE`です。  
  
## <a name="see-also"></a>参照  
 [ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)