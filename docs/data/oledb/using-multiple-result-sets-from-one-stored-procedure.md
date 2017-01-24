---
title: "1 つのストアド プロシージャからの複数の結果セットの使用 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "複数結果セット"
  - "ストアド プロシージャ, 返す (結果セットを)"
ms.assetid: c450c12c-a76c-4ae4-9675-071a41eeac05
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 1 つのストアド プロシージャからの複数の結果セットの使用
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ほとんどのストアド プロシージャは複数の結果セットを返します。  このようなストアド プロシージャには、通常は 1 つ以上の SELECT ステートメントが含まれます。  コンシューマーは、この点を考慮してすべての結果セットを処理する必要があります。  
  
### 複数の結果セットを処理するには  
  
1.  `CMultipleResults` をテンプレート引数とし、任意のアクセサーを使用して `CCommand` クラスを作成します。  通常は、動的アクセサーまたは手動アクセサーを使用します。  他の種類のアクセサーを使用すると、各行セットの出力列を判断できない場合があります。  
  
2.  通常どおりにストアド プロシージャを実行し、列を連結します。「[データのフェッチ](../../data/oledb/fetching-data.md)」を参照してください。  
  
3.  データを使用します。  
  
4.  `CCommand` クラスで `GetNextResult` を呼び出します。  別の結果行セットが使用可能な場合、`GetNextResult` は S\_OK を返します。手動アクセサーを使用している場合は、列を再連結する必要があります。  `GetNextResult` からエラーが返された場合、使用可能な結果セットはありません。  
  
## 参照  
 [ストアド プロシージャの使用](../../data/oledb/using-stored-procedures.md)