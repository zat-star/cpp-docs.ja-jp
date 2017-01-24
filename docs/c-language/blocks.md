---
title: "Blocks | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "ブロック"
  - "compound ステートメント"
  - "関数定義, コード内のブロック"
  - "ステートメント, 複合"
ms.assetid: be231a92-c712-464e-ae25-a4becb20f7f5
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Blocks
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

中かっこ \(**{ }**\) で囲まれた一連の宣言、定義、ステートメントを "ブロック" といいます。 C には 2 種類のブロックがあります。  その 1 つは、1 つ以上のステートメントで構成される "複合ステートメント" です \(「[複合ステートメント](../c-language/compound-statement-c.md)」を参照\)。  もう 1 つの "関数定義" は、複合ステートメント \(関数本体\) とその関数のヘッダー \(関数名、戻り値の型、仮パラメーター\) で構成されます。  ブロック内に他のブロックが挿入された状態を "入れ子" といいます。  
  
 複合ステートメントはすべて中かっこで囲まれますが、中かっこで囲まれたすべてが複合ステートメントではないことに注意してください。  たとえば、配列、構造体、または列挙体の要素を指定する際に中かっこで囲む場合がありますが、これらは複合ステートメントではありません。  
  
## 参照  
 [ソース ファイルとソース プログラム](../c-language/source-files-and-source-programs.md)