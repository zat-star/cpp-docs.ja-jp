---
title: "_CIlog10 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CIlog10"
apilocation: 
  - "msvcr100.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "CIlog10"
  - "_CIlog10"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CIlog10 組み込み"
  - "CIlog10 組み込み"
ms.assetid: 05d7fcaa-3cff-4cc5-8d44-015e7cacba24
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CIlog10
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

スタック上に値の `log10` 操作を実行します。  
  
## 構文  
  
```  
void __cdecl _CIlog10();  
```  
  
## 解説  
 `log10` 関数のこのバージョンにコンパイラが示すことがわかる特殊な呼び出し規約があります。  関数は、コピーは生成される高速化し、レジスタの割り当てとことを防ぐために実行されます。  
  
 結果値はスタックの上部に挿入されます。  
  
## 必要条件  
 **プラットフォーム:** x86  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [log、logf、log10、log10f](../Topic/log,%20logf,%20log10,%20log10f.md)