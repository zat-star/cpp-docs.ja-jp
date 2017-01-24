---
title: "コンパイラ エラー C2414 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2414"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2414"
ms.assetid: bbe94e03-862e-4990-b15e-544ae464727d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2414
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

オペランドの数が正しくありません。  
  
### 次のような原因をチェックして問題を解決するには  
  
1.  オペコードに使われているオペランドの数が正しくありません。  アセンブリ言語のリファレンス マニュアルで、正しいオペランド数を調べてください。  
  
2.  最近のプロセッサでは、オペランド数が異なる命令もサポートされます。  低速なプロセッサを使用する場合は、[\/arch \(最小限の CPU アーキテクチャ\)](../../build/reference/arch-minimum-cpu-architecture.md) オプションを調整します。