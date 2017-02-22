---
title: "抽出エラーのテスト | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "抽出エラー"
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 抽出エラーのテスト
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[エラー処理機能](../standard-library/output-file-stream-member-functions.md)で説明されている出力エラー処理機能は入力ストリームに適用されます。  抽出中のエラーのテストが重要です。  このステートメントを検討する:  
  
```  
cin >> n;  
```  
  
 が 32,767 \(最大値、または MAX\_INT\) ストリームの `fail` ビットと `cin` オブジェクトを、使用不可能に設定する `n` が符号付き整数であるか、最大値です。  すべての後続の抽出は、格納されている値を持たない直接の値になります。  
  
## 参照  
 [入力ストリーム](../standard-library/input-streams.md)