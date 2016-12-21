---
title: "リンカ ツール エラー LNK1302 | Microsoft Docs"
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
  - "LNK1302"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1302"
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカ ツール エラー LNK1302
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

リンクに安全な .netmodules; リンク ファイル"に存在しない  
  
 .netmodule \(**\/LN**を指定してコンパイルされた\) MSIL リンクを呼び出すユーザーのリンカーに渡されました。C\+\+ モジュールは、**\/clr:safe** でコンパイルされている場合は、MSIL リンクで有効です。  
  
 このエラーを修正するには、**\/clr:safe** を指定してコンパイルして MSIL リンクを有効にするか、モジュールの代わりに **\/clr** または **\/clr:pure** .obj ファイルをリンカーに渡します。  
  
 詳細については、次のトピックを参照してください  
  
-   [\/LN \(MSIL モジュールの作成\)](../../build/reference/ln-create-msil-module.md)  
  
-   [リンカー入力としての .netmodule ファイル](../Topic/.netmodule%20Files%20as%20Linker%20Input.md)