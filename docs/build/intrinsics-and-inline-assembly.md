---
title: "組み込みおよびインライン アセンブリ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 8affd4bb-279d-46f3-851f-8be0a9c5ed3f
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 組み込みおよびインライン アセンブリ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vcprx64](../Token/vcprx64_md.md)] コンパイラの制約の 1 つに、インライン アセンブラーがサポートされていないことが挙げられます。  これは、C または C\+\+ で記述できない関数は、サブルーチンとして記述するか、コンパイラがサポートする組み込み関数として記述する必要があることを意味します。  特定の関数はパフォーマンス センシティブですが、それ以外の関数はパフォーマンス センシティブではありません。  パフォーマンス センシティブである関数は、組み込み関数として実装する必要があります。  
  
 コンパイラがサポートしている組み込みの詳細については、「[コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)」を参照してください。  
  
## 参照  
 [x64 ソフトウェア規約](../build/x64-software-conventions.md)