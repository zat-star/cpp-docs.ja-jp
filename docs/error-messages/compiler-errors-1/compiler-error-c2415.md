---
title: "コンパイラ エラー C2415 | Microsoft Docs"
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
  - "C2415"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2415"
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2415
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

オペランドの型が無効です。  
  
 このオペコードは、この型のオペランドを使いません。  
  
### 次のような原因をチェックして問題を解決するには  
  
1.  オペコードに使われているオペランドの数が正しくありません。  アセンブリ言語のリファレンス マニュアルで、正しいオペランド数を調べてください。  
  
2.  最近のプロセッサでは、別の型を使用する命令もサポートされます。  低速なプロセッサを使用する場合は、[\/arch \(最小限の CPU アーキテクチャ\)](../../build/reference/arch-minimum-cpu-architecture.md) オプションを調整します。