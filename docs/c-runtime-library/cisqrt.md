---
title: "_CIsqrt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CIsqrt"
apilocation: 
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_CIsqrt"
  - "CIsqrt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CIsqrt 組み込み"
  - "_CIsqrt 組み込み"
ms.assetid: 663548ea-398c-48ee-8397-a787c6ebb937
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# _CIsqrt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

スタックの最上位値の平方根を計算します。  
  
## 構文  
  
```  
void __cdecl _CIsqrt();  
```  
  
## 解説  
 `sqrt` 関数のこのバージョンにコンパイラが示すことがわかる特殊な呼び出し規約があります。  また、コピーは生成される高速化し、レジスタの割り当てとことを防ぐために実行されます。  
  
 結果値はスタックの上部に挿入されます。  
  
## 必要条件  
 **プラットフォーム:** x86  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [sqrt、sqrtf、sqrtl](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)