---
title: "リンカー入力としての .pdb ファイル | Microsoft Docs"
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
  - ".pdb ファイル, リンカー入力としての"
  - "PDB ファイル, リンカー入力としての"
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカー入力としての .pdb ファイル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/Zi オプションでコンパイルしたオブジェクト \(.obj\) ファイルには、プログラム データベース \(PDB ファイル\) の名前が記述されています。  リンクするオブジェクトの PDB ファイル名をリンカーに対して指示する必要はありません。PDB ファイルが必要になると、LINK がオブジェクト ファイルに書き込まれたファイル名を参照して PDB ファイルを探します。  ライブラリに登録されているデバッグ可能なオブジェクトの場合も同じです。したがって、デバッグ可能なライブラリに対する PDB ファイルは、ライブラリ本体と同じように、リンカーが検索できるところに置く必要があります。  
  
 PDB ファイルには、.exe ファイルや .dll ファイルのデバッグ情報も保存されます。  プログラムをビルドし直すと PDB ファイルが更新されるため、プログラム用の PDB ファイルはリンカーにとって入力ファイルであると同時に出力ファイルでもあります。  
  
## 参照  
 [LINK の入力ファイル](../../build/reference/link-input-files.md)   
 [リンカー オプション](../../build/reference/linker-options.md)