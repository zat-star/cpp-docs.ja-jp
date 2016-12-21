---
title: "記述ブロック | Microsoft Docs"
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
  - "ブロック, 記述"
  - "記述ブロック"
  - "NMAKE プログラム, 記述ブロック"
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 記述ブロック
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

記述ブロックは依存関係行であり、必要に応じてコマンド ブロックが後に続きます。  
  
```  
targets... : dependents...  
    commands...  
```  
  
 依存関係行では、1 つ以上のターゲットと 0 個以上の依存ファイルを指定します。  ターゲットは、行の先頭で指定する必要があります。  ターゲットと依存ファイルはコロン \(:\) で区切ります。依存関係行では空白やタブを使用できます。  行を分割するには、ターゲットまたは依存ファイルの後に円記号 \(\\\) を使用します。  ターゲットが存在しない場合、ターゲットのタイムスタンプが依存ファイルのタイムスタンプより古い場合、またはターゲットが[疑似ターゲット](../build/pseudotargets.md)である場合、NMAKE はコマンドを実行します。  依存ファイルがほかの依存関係行ではターゲットである場合、その依存ファイルが存在しないか、またはそれ自身の依存ファイルと比べて古いと、現在の依存関係の更新前に依存ファイルが更新されます。  
  
## さらに詳しくは次のトピックをクリックしてください  
 [ターゲット](../build/targets.md)  
  
 [依存ファイル](../build/dependents.md)  
  
## 参照  
 [NMAKE リファレンス](../build/nmake-reference.md)