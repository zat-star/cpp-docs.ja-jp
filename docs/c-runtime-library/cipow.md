---
title: "_CIpow | Microsoft Docs"
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
  - "_CIpow"
apilocation: 
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "msvcrt.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "CIpow"
  - "_CIpow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CIpow 組み込み"
  - "_CIpow 組み込み"
ms.assetid: 477aaf0c-ac58-4252-89dd-9f3e35d47536
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CIpow
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

スタックの最上位値に基づいて *y* の機能を発生させる *x* を計算します。  
  
## 構文  
  
```  
void __cdecl _CIpow();  
```  
  
## 解説  
 `pow` 関数のこのバージョンにコンパイラが示すことがわかる特殊な呼び出し規約があります。  また、コピーは生成される高速化し、レジスタの割り当てとことを防ぐために実行されます。  
  
 結果値はスタックの上部に挿入されます。  
  
## 必要条件  
 **プラットフォーム:** x86  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [pow、powf、powl](../Topic/pow,%20powf,%20powl.md)