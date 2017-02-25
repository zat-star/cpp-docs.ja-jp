---
title: "ML Error Messages | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.errors.ml"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MASM (Microsoft Macro Assembler), ML error messages"
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# ML Error Messages
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MASM コンポーネントによって生成されたエラー メッセージは 3 種類に分類されています :  
  
-   **致命的なエラー。**これらはユーティリティが正常な処理を完了できない重大な問題について説明します。  
  
-   **的でないエラー。**ユーティリティはプロセスを実行する場合があります。  これは結果が必要なものとして可能性の低いです。  
  
-   **警告。**これらのメッセージは必要な結果を得ることができない場合がある条件を示します。  
  
 すべてのエラー メッセージは次のとおりです。:  
  
```  
  
Utility: Filename (Line) : [Error_type} (Code): Message_text  
```  
  
 それぞれの文字について以下に説明します。  
  
 `Utility`  
 エラー メッセージを送信できます。  
  
 *fileName*  
 エラーを生成する条件を含むファイル。  
  
 *Line*  
 エラー条件です。おおよその行。  
  
 *Error\_type*  
 致命的なエラーエラー警告です。  
  
 *コード*  
 一意の 5 ビットまたは 6 桁のエラー コードを返します。  
  
 `Message_text`  
 エラー条件の短縮一般的な説明。  
  
## 参照  
 [Microsoft Macro Assembler Reference](../../assembler/masm/microsoft-macro-assembler-reference.md)