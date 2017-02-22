---
title: "リンカー ツールの警告 LNK4102 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4102"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4102"
ms.assetid: bfd1b17e-05c7-4bc2-80d6-2888b1a425b2
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# リンカー ツールの警告 LNK4102
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

削除するデストラクター 'name' のエクスポートです。イメージは正しく動作しない可能性があります。  
  
 削除するデストラクターのエクスポートを試みました。  DLL 境界を越えて **delete** し、プロセスが所有していないメモリを解放することがあります。  指定したシンボルが、.def ファイルに記述されていないことを確認してください。また、リンカーのコマンド ラインの **\/IMPORT** オプションまたは **\/EXPORT** オプションの引数として記述されていないことを確認してください。  
  
 C ランタイム ライブラリを再度ビルドする場合は、このメッセージを無視してかまいません。