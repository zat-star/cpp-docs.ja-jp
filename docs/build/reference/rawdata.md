---
title: "/RAWDATA | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/rawdata"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/RAWDATA dumpbin オプション"
  - "生データ"
  - "RAWDATA dumpbin オプション"
  - "-RAWDATA dumpbin オプション"
ms.assetid: 41cba845-5e1f-415e-9fe4-604a52235983
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /RAWDATA
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/RAWDATA[:{1|2|4|8|NONE[,number]]  
```  
  
## 解説  
 このオプションは、ファイルの各セクションの生のコンテンツを出力します。  引数によって、出力形式を指定できます。次の表は、引数とその出力形式をまとめたものです。  
  
|引数|結果|  
|--------|--------|  
|1|これが既定値です。  16 進形式でバイト列を出力します。ASCII 形式で出力できる場合は、ASCII 文字も出力します。|  
|2|内容は 2 バイトの 16 進数値で表示されます。|  
|4|内容は 4 バイトの 16 進数値で表示されます。|  
|8|内容は 8 バイトの 16 進数値で表示されます。|  
|NONE|生のデータが表示されなくなります。  \/ALL の出力を制御する場合に使用します。|  
|*数値*|`number` 個の値を出力できるように行幅を設定します。|  
  
 [\/GL](../../build/reference/gl-whole-program-optimization.md) コンパイラ オプションで生成したファイルで使用できるのは、[\/HEADERS](../../build/reference/headers.md) DUMPBIN オプションだけです。  
  
## 参照  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)