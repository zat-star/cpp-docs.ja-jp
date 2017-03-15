---
title: "ANSI C 準拠 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Ansi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ANSI [C++], C 規格"
  - "互換性 [C++], ANSI C"
  - "準拠 (ANSI C に)"
  - "規則 [C++], Microsoft 拡張機能"
  - "Microsoft 拡張機能の名前付け規則"
  - "名前付け規則 [C++], Microsoft ライブラリ"
  - "アンダースコア (_)"
  - "アンダースコア (_), 先行する"
ms.assetid: 6be271bf-eecf-491a-a928-0ee2dd60e3b9
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ANSI C 準拠
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ランタイム システムのすべての Microsoft 固有の ID の名前付け規則 \(関数、マクロ、定数、変数、型定義など\) ANSI 準拠です。  このドキュメントでは、ANSI\/ISO C の標準に準拠したランタイム関数は注意して互換 ANSI として。  ANSI 準拠アプリケーションはこれらの ANSI 互換性のある関数を使用してください。  
  
 Microsoft 固有の関数とグローバル変数には、名前にアンダースコア \(\) が付きます。  これらの名前は、コードの範囲内では、ローカルにのみをオーバーライドできます。  たとえば、Microsoft のランタイム ヘッダー ファイルが含まれる場合、場合も、ローカルに同じ名前のローカル変数を宣言すると、`_open` という名前の Microsoft 固有の関数をオーバーライドできます。  ただし、独自のグローバル関数またはグローバル変数の場合、この名前は使用できません。  
  
 Microsoft 固有のマクロとマニフェスト定数の名前は 2 個のアンダースコア \(またはすぐに大文字に続く一つの先頭にアンダースコア \(\) が付きます。  これらの ID のスコープは、絶対です。  たとえば、Microsoft 固有の ID **\_UPPER** のこのような理由で使用できません。  
  
## 参照  
 [互換性](../c-runtime-library/compatibility.md)