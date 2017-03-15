---
title: "リンカー入力としての .exp ファイル | Microsoft Docs"
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
  - ".exp ファイル [C++]"
  - "EXP ファイル"
  - "エクスポート (データを), エクスポート (.exp) ファイル"
  - "エクスポート (関数を)"
  - "エクスポート (関数を), 情報 (エクスポート関数に関する)"
  - "関数 [C++], エクスポート"
  - "インポート ライブラリ, リンカー ファイル"
  - "リンク [C++], エクスポート"
ms.assetid: 399f5636-0a4d-462e-b500-5f5b9ae5ad22
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカー入力としての .exp ファイル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

エクスポート \(.exp\) ファイルの内容は、エクスポートされる関数やデータ項目に関する情報です。  LIB ツールでインポート ライブラリを作成すると、同時に .exp ファイルも作成されます。  この .exp ファイルを使うのは、別のプログラムとの間で直接または間接的に、エクスポートとインポートを行うプログラムをリンクするときです。  .exp ファイルを使ってリンクすると、LIB で既にインポート ライブラリが生成されていると見なされ、インポート ライブラリは新しく作成されません。  .exp ファイルとインポート ライブラリについては、「[インポート ライブラリとエクスポート ファイル](../../build/reference/working-with-import-libraries-and-export-files.md)」を参照してください。  
  
## 参照  
 [LINK の入力ファイル](../../build/reference/link-input-files.md)   
 [リンカー オプション](../../build/reference/linker-options.md)