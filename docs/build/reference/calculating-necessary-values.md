---
title: "必要な値の計算 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
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
  - "ヘルパー関数, 計算 (必要な値を)"
ms.assetid: 4f037d0f-881a-4a48-a9d2-9f8872dfccb7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 必要な値の計算
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

遅延読み込みヘルパー ルーチンでは、2 つの重要な情報を計算する必要があります。  これらの情報を計算するために、delayhlp.cpp には次の 2 つのインライン関数が用意されています。  
  
-   1 番目の関数は、現在のインポートのインデックスを計算して、インポート アドレス テーブル \(IAT: Import Address Table\)、バインドされたインポート アドレス テーブル \(BIAT: Bound Import Address Table\)、および非バインド インポート アドレス テーブル \(UIAT: Unbound Import Address Table\) の 3 つの異なるテーブルに格納します。  
  
-   2 番目の関数は、有効な IAT 内のインポート数をカウントします。  
  
```  
// utility function for calculating the index of the current import  
// for all the tables (INT, BIAT, UIAT, and IAT).  
__inline unsigned  
IndexFromPImgThunkData(PCImgThunkData pitdCur, PCImgThunkData pitdBase) {  
    return pitdCur - pitdBase;  
    }  
  
// utility function for calculating the count of imports given the base  
// of the IAT. NB: this only works on a valid IAT!  
__inline unsigned  
CountOfImports(PCImgThunkData pitdBase) {  
    unsigned        cRet = 0;  
    PCImgThunkData  pitd = pitdBase;  
    while (pitd->u1.Function) {  
        pitd++;  
        cRet++;  
        }  
    return cRet;  
    }  
```  
  
## 参照  
 [Understanding the Helper Function](http://msdn.microsoft.com/ja-jp/6279c12c-d908-4967-b0b3-cabfc3e91d3d)