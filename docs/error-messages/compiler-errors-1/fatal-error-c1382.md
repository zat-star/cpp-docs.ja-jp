---
title: "致命的なエラー C1382 | Microsoft Docs"
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
  - "C1382"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1382"
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 致命的なエラー C1382
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

PCH ファイル 'file' は、'obj' が生成された後リビルドされています。このオブジェクトをリビルドしてください。  
  
 [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md) を使用している場合に、コンパイラは、.pch ファイルが指している CIL .obj よりも、その .pch ファイルの方が新しいことを検出しました。  CIL .obj ファイル内の情報が最新ではありません。  オブジェクトを再度ビルドしてください。  
  
 C1382 は、**\/Yc** を指定しているにもかかわらず、複数のソース コード ファイルをコンパイルに渡してコンパイルした場合にも発生することがあります。このエラーを解決するには、コンパイラに複数のソース コード ファイルを渡すときに **\/Yc** を指定しないでください。詳細については、「[\/Yc \(プリコンパイル済みヘッダー ファイルの作成\)](../../build/reference/yc-create-precompiled-header-file.md)」を参照してください。