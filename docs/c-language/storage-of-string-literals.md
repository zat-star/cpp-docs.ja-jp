---
title: "文字列リテラルの格納 | Microsoft Docs"
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
  - "リテラル文字列, ストレージ"
ms.assetid: ba5e4d2c-d456-44b3-a8ca-354af547ac50
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 文字列リテラルの格納
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リテラル文字列の各文字は、連続するメモリ位置に順番に格納されます。  リテラル文字列内のエスケープ シーケンス \(**\\\\** や **\\"** など\) は、それぞれ 1 文字としてカウントされます。  \(**\\0** エスケープ シーケンスによって表される\) null 文字は各文字列リテラルに自動的に追加され、その最後を示します  \(これは[変換フェーズ](../preprocessor/phases-of-translation.md) 7 で発生します\)。2 つの同じ文字列が別々のアドレスに保存されない場合があることに注意してください。  [\/GF](../Topic/-GF%20\(Eliminate%20Duplicate%20Strings\).md) を指定すると、同じ文字列が複数ある場合に、その 1 つだけが実行可能ファイルに追加されます。  
  
## 解説  
 **Microsoft 固有の仕様 →**  
  
 文字列には、静的ストレージ存続期間があります。  ストレージ存続期間については、「[ストレージ クラス](../c-language/c-storage-classes.md)」を参照してください。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [C 文字列リテラル](../c-language/c-string-literals.md)