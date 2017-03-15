---
title: "Building an Attributed Program | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tlb files"
  - "MIDL"
  - "MIDL, linker output"
  - "IDL files"
  - "tlb files, building attributed programs"
  - ".tlb files, building attributed programs"
  - "IDL files, building"
  - "attributes [C++], building type libraries and .idl files"
  - ".tlb files"
  - ".idl files, building"
  - "type libraries, linker options for building"
ms.assetid: 04997b5f-bf2c-46ec-b868-c4adebbef5f4
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Building an Attributed Program
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ソース・コードにはVisual C\+\+ 属性を送信するとVisual C\+\+ コンパイラはのタイプ ライブラリと .idl ファイルを生成することができます。  次のリンカー オプションは.tlb\) ファイルを作成できます :  
  
-   [\/IDLOUT](../Topic/-IDLOUT%20\(Name%20MIDL%20Output%20Files\).md)  
  
-   [\/IGNOREIDL](../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)  
  
-   [\/MIDL](../build/reference/midl-specify-midl-command-line-options.md)  
  
-   [\/TLBOUT](../build/reference/tlbout-name-dot-tlb-file.md)  
  
 あるプロジェクトに複数の依存しない .idl ファイルが含まれています。  これらが複数の .tlb ファイルを作成しオプションでリソースがブロックにバインドするために使用されます。  このシナリオはVisual C\+\+ で現在サポートされていません。  
  
 またVisual C\+\+ リンカーは単一の MIDL のファイルに関連するすべての IDL 属性情報を出力します。  単一のプロジェクトで 2 種類のタイプ ライブラリを生成する方法はありません。  
  
## 参照  
 [Concepts](../windows/attributed-programming-concepts.md)