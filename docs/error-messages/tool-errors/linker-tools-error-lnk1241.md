---
title: "リンカ ツール エラー LNK1241 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1241"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1241"
ms.assetid: 7b8b52eb-0231-4521-b52a-2bce8d3e8956
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# リンカ ツール エラー LNK1241
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

リソース ファイル 'resource file' は既に指定されています。  
  
 このエラーは、**cvtres** をコマンド ラインから直接実行し、その結果の .obj ファイルを他の .res ファイルと共にリンカーに渡した場合に発生します。  
  
 複数の .res ファイルを指定するには、**cvtres** で作成された .obj ファイルからではなく、すべてを .res ファイルとしてリンカーに渡します。