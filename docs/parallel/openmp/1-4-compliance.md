---
title: "1.4 準拠 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 662ad260-b9a1-43b7-b269-ef6ff0714e05
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 1.4 準拠
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OpenMP C と C++ API の実装は、 *OpenMP 準拠* かどうか認識し、第 1 章、2、3、4、レイアウトとは、この仕様のすべての要素のセマンティクスを保持しており付録 C A、B、D、E、および F は情報目的のみの場合、仕様の一部ではないです。 API のサブセットのみを含む実装は、OpenMP 準拠していません。  
  
 OpenMP C および C++ API の実装でサポートされているベース言語拡張であります。 基本言語は、このドキュメントで言語構成要素または表示拡張機能をサポートしない場合、OpenMP の実装をサポートするためには不要です。  
  
 すべての C および C++ の標準ライブラリ関数と組み込み関数 (つまり、コンパイラが特定のナレッジには、関数) スレッド セーフである必要があります。 並列領域内の別のスレッドでスレッド セーフな関数の非同期の使用には、未定義の動作は発生しません。 ただし、動作はありませんシリアル領域と同じです。 (ランダムな番号の生成機能は、例を示します)。  
  
 特定の動作があることを指定 OpenMP C と C++ API *実装で定義されます。* OpenMP に準拠した実装を定義し、このような場合は、その動作を文書化する必要があります。 参照してください [付録 E](../Topic/E.%20Implementation-Defined%20Behaviors%20in%20OpenMP%20C-C++.md), 、実装で定義される動作の一覧については、97 ページです。