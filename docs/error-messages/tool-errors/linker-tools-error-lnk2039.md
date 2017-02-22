---
title: "リンカ ツール エラー LNK2039 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2039"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2039"
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# リンカ ツール エラー LNK2039
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

another.obj で定義 '\<\>' されている ref クラス型をインポートします; これは、インポートされるか、定義することはできません。  
  
 ref クラス '\<`type`は指定\>' された .obj ファイルでインポートされますが、別の .obj ファイルに定義されています。  この条件により実行時エラーまたはそのほかの予測できない動作が発生する可能性があります。  
  
### このエラーを解決するには  
  
1.  .winmd ファイルからインポートするか '`type`' が他の .obj ファイルとチェックで定義する必要があるかどうかを確認します。  
  
2.  定義のインポートを削除します。  
  
## 参照  
 [リンカー ツール エラーと警告](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)   
 [リンカ ツール エラー LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)