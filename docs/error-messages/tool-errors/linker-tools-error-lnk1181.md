---
title: "リンカ ツール エラー LNK1181 | Microsoft Docs"
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
  - "LNK1181"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1181"
ms.assetid: 984b0db6-e331-4284-b2a7-a212fe96c486
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカ ツール エラー LNK1181
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

入力ファイル 'filename' を開けません。  
  
 `filename` のファイルが存在しないか、パスが見つからないため、リンカーはこのファイルを見つけることができません。  
  
 一般に、エラー LNK1181 が発生する原因として次のことが考えられます。  
  
-   リンカーのコマンド ラインに追加の依存ファイルとして `filename` が参照されていますが、そのファイルが存在しません。  
  
-   `filename` が格納されたディレクトリを指定する **\/LIBPATH** ステートメントが欠落しています。  
  
 上の問題を解決するためには、リンカーのコマンド ラインで参照されたすべてのファイルがシステムに存在している必要があります。さらに、リンカーの依存ファイルが格納されている各ディレクトリについて、**\/LIBPATH** ステートメントが存在する必要があります。  
  
 もう 1 つ考えられる原因として、空白を含む長いファイル名が引用符で囲まれていない場合に、LNK1181 が発生することがあります。この場合、リンカーは最初の空白までのみをファイル名と認識し、ファイル拡張子を .obj とします。この状況を解決するには、長いファイル名 \(パスとファイル名\) を引用符で囲みます。  
  
 詳細については、「[リンカー入力としての .lib ファイル](../../build/reference/dot-lib-files-as-linker-input.md)」を参照してください。  
  
## 参照  
 [\/LIBPATH \(追加ライブラリのパス\)](../../build/reference/libpath-additional-libpath.md)