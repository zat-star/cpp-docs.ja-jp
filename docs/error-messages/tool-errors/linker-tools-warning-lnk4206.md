---
title: "リンカー ツールの警告 LNK4206 | Microsoft Docs"
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
  - "LNK4206"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4206"
ms.assetid: 6c108e33-00cf-4c5a-830d-d65d470930a7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカー ツールの警告 LNK4206
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プリコンパイル済みの型情報が見つかりません。'filename' はリンクしていないか、上書きされています。デバッグ情報を無視してオブジェクトをリンクします。  
  
 [\/Yc](../../build/reference/yc-create-precompiled-header-file.md) オプションを指定してコンパイルされたオブジェクト ファイルが、LINK コマンドで指定されていないか、または上書きされています。  
  
 一般にこの警告は、\/Yc オプションを指定してコンパイルされた .obj ファイルがライブラリ内にあるにもかかわらず、この .obj ファイルを参照するシンボルがコードにない場合に発生します。この場合、リンカーはこの .obj ファイルを使用しません。参照もしません。このような場合には、コードを再コンパイルし、残りのオブジェクト \(\/Yc を指定してコンパイルされていないオブジェクト\) に対して [\/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) を使用します。