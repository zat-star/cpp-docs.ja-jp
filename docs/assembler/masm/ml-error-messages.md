---
title: "ML エラー メッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.errors.ml
dev_langs: C++
helpviewer_keywords: MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1fa5933c9c676b76ebe342ffa848e7b40926da08
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ml-error-messages"></a>ML エラー メッセージ
MASM のコンポーネントによって生成されたエラー メッセージは、3 つのカテゴリに分類されます。  
  
-   **致命的なエラー。** これらをユーティリティが通常のプロセスを完了するを妨げる重大な問題を示します。  
  
-   **致命的でないエラーです。** ユーティリティは、そのプロセスを完了可能性があります。 場合は、その結果は希望する可能性があります。  
  
-   **警告です。** これらのメッセージは、目的の結果を得られない可能性がありますの状態を示します。  
  
 すべてのエラー メッセージは、次の形式をとります。  
  
```  
  
Utility: Filename (Line) : [Error_type} (Code): Message_text  
```  
  
 それぞれの文字について以下に説明します。  
  
 `Utility`  
 エラー メッセージを送信するプログラム。  
  
 *ファイル名*  
 エラーが発生する条件を含むファイルです。  
  
 *Line*  
 エラー条件が存在するおおよその行番号。  
  
 *Error_type*  
 致命的なエラー、エラー、または警告です。  
  
 *コード*  
 一意の 5 または 6 桁のエラー コード。  
  
 `Message_text`  
 短期的および一般的なエラー状態の説明です。  
  
## <a name="see-also"></a>参照  
 [Microsoft Macro Assembler リファレンス](../../assembler/masm/microsoft-macro-assembler-reference.md)