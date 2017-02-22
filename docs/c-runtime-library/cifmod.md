---
title: "_CIfmod | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CIfmod"
apilocation: 
  - "msvcrt.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_CIfmod"
  - "CIfmod"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CIfmod 組み込み"
  - "_CIfmod 組み込み"
ms.assetid: 7c050653-7ec6-4810-b3a7-7a0057ea65ed
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# _CIfmod
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

スタックの最上位の値 2 浮動小数点の剰余を計算します。  
  
## 構文  
  
```  
void __cdecl _CIfmod();  
```  
  
## 解説  
 `fmod` 関数のこのバージョンにコンパイラが示すことがわかる特殊な呼び出し規約があります。  また、コピーは生成される高速化し、レジスタの割り当てとことを防ぐために実行されます。  
  
 結果値はスタックの上部に挿入されます。  
  
## 必要条件  
 **プラットフォーム:** x86  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fmod、fmodf](../Topic/fmod,%20fmodf.md)