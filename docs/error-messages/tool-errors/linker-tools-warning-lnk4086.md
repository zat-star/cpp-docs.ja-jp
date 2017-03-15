---
title: "リンカー ツールの警告 LNK4086 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4086"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4086"
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# リンカー ツールの警告 LNK4086
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

エントリポイント '関数' は '数値' バイトの引数を持つ \_\_stdcall ではありません。イメージは動作しない可能性があります。  
  
 DLL のエントリ ポイントは `__stdcall` であることが必要です。  [\/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md) オプションで関数を再コンパイルするか、関数を定義するときに、`__stdcall` または WINAPI を指定してください。