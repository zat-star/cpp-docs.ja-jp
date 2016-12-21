---
title: "リンカ ツール エラー LNK2008 | Microsoft Docs"
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
  - "LNK2008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2008"
ms.assetid: bbcd83c5-c8ae-439e-a033-63643a5bb373
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカ ツール エラー LNK2008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

fixup のターゲットが 'symbol\_name' にアライメントされていません。  
  
 LINK はオブジェクト ファイルにフィックスアップのターゲットを発見しましたが、このファイルの配置は正しくありません。  
  
 このエラーは、カスタムのセクション配置 \(たとえば \#pragma [pack](../../preprocessor/pack.md)\) や [align](../../cpp/align-cpp.md) 修飾子によって、またはセクション配置を変更するアセンブリ言語コードを使用することによって発生する場合があります。  
  
 コードで上記のいずれも使用していない場合は、コンパイラが原因である可能性があります。