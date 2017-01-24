---
title: "/MANIFESTINPUT (マニフェスト入力の指定) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /MANIFESTINPUT (マニフェスト入力の指定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マニフェスト入力ファイルをイメージに埋め込まれたマニフェストに含めるように指定します。  
  
## 構文  
  
```c#  
/MANIFESTINPUT:filename  
```  
  
#### パラメーター  
 `filename`  
 埋め込みマニフェストに含めるマニフェスト ファイル。  
  
## 解説  
 **\/MANIFESTINPUT** オプションは、実行可能イメージに埋め込みマニフェストを作成するために使用する入力ファイルのパスを指定します。  複数のマニフェスト入力ファイルがある場合は、スイッチを複数回使用します \(入力ファイルごとに 1 回\)。  マニフェスト入力ファイルは埋め込みマニフェストを作成するためにマージされます。  このオプションには **\/MANIFEST:EMBED** オプションが必要です。  
  
 このオプションは [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] で直接設定することはできません。  代わりに、追加のマニフェスト ファイルを含めるように指定するプロジェクトの **\[追加のマニフェスト ファイル\]** のプロパティを使用します。  詳細については、「[\[入力と出力\] \(\[\<プロジェクト名\> プロパティ ページ\] ダイアログ ボックス \- \[構成プロパティ\] \- \[マニフェスト ツール\]\)](../Topic/Input%20and%20Output,%20Manifest%20Tool,%20Configuration%20Properties,%20%3CProjectname%3E%20Property%20Pages%20Dialog%20Box.md)」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)