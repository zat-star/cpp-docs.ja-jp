---
title: "リンカー ツールの警告 LNK4070 | Microsoft Docs"
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
  - "LNK4070"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4070"
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカー ツールの警告 LNK4070
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

.EXP 内の \/OUT:filename ディレクティブの指定が出力ファイル名 'filename' と異なっています。ディレクティブは無視されます。  
  
 .exp ファイルが作成されたときに [NAME](../Topic/NAME%20\(C-C++\).md) ステートメントまたは [LIBRARY](../../build/reference/library.md) ステートメントで指定された `filename` が、既定で設定された出力の `filename`、または [\/OUT](../../build/reference/out-output-file-name.md) オプションで指定された filename と異なっています。  
  
 この警告は、開発環境で出力ファイル名を変更し、プロジェクトの .def ファイルが更新されなかった場合に生成されます。  この警告を解決するには、.def ファイルを手動で更新します。  
  
 作成される DLL を使用したクライアント プログラムで、問題が発生する可能性があります。