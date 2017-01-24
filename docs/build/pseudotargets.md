---
title: "疑似ターゲット | Microsoft Docs"
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
helpviewer_keywords: 
  - "メイクファイル, 擬似ターゲット"
  - "NMAKE プログラム, 擬似ターゲット"
  - "NMAKE プログラム, ターゲット"
  - "擬似ターゲットと NMAKE"
  - "タイムスタンプ, メイクファイルの擬似ターゲット"
ms.assetid: c8c479dc-0129-4186-8366-bc6251f2b494
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 疑似ターゲット
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

疑似ターゲットは、依存関係行でファイル名の代わりに使用されるラベルです。  疑似ターゲットは、存在しない、古いファイルとして解釈されます。  NMAKE は、疑似ターゲットのタイムスタンプが、すべての依存ファイルの中で最も新しいタイムスタンプであると仮定します。  依存ファイルがない場合は、現在の時刻と仮定されます。  疑似ターゲットがターゲットとして使用される場合、そのコマンドは常に実行されます。  依存ファイルとして指定できるのは、ほかの依存関係でターゲットとして指定されている擬似ターゲットだけです。  ただし、その依存関係にコマンド ブロックは必要ありません。  
  
 疑似ターゲットの名前は、ターゲットのファイル名構文規則に従います。  ただし、名前に拡張子がない場合、つまり名前にピリオドが含まれていない場合は、ファイル名の 8 文字制限を無視して 256 文字まで使用できます。  
  
## 参照  
 [ターゲット](../build/targets.md)