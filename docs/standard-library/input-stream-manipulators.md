---
title: "入力ストリーム マニピュレーター | Microsoft Docs"
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
  - "入力ストリーム オブジェクト"
  - "入力ストリーム, マニピュレーター"
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 入力ストリーム マニピュレーター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

多くのマニピュレーターは、[setprecision](../Topic/setprecision.md)などの `ios` クラスに定義され、入力ストリームとして適用されます。  ただし、マニピュレーターは実際には入力ストリーム オブジェクトに影響します。  これは、最上位の入力ストリームから数で使用される変換基数を決定する基数のマニピュレーター、`dec`、`oct`と `hex`です。  
  
 抽出で、`hex` のマニピュレーターはさまざまな形式で入力処理を有効にします。  たとえば、c、C、0xc、0xC、0Xc と 0XC は、10 進整数 12 として解釈されます。  0 ~ 9、A ~ F、および a ~ f x、X 以外の文字が数値変換を終了します。  したがって `"124n5"` シーケンスは [basic\_ios::fail](../Topic/basic_ios::fail.md) のビットが設定されている第 124 に変換されます。  
  
## 参照  
 [入力ストリーム](../standard-library/input-streams.md)