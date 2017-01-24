---
title: "コンパイラの警告 (レベル 1) C4041 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4041"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4041"
ms.assetid: 107ee9fd-4b88-4f22-a18f-a20726831095
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4041
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンパイラの制限 : ブラウザーの出力を中止します。  
  
 ブラウザー情報がコンパイラの制限を超えました。  
  
 この警告は、[\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) \(ローカル変数を含めたブラウザー情報\) でコンパイルすると発生することがあります。  
  
### 修復の可能性がある解決策  
  
1.  \/Fr \(ローカル変数を含まないブラウザー情報\) でコンパイルします。  
  
2.  ブラウザーの出力 \(\/FR や \/Fr なしのコンパイル\) を無効にします。