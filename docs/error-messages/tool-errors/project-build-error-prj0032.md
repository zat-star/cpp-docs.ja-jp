---
title: "プロジェクト ビルド エラー PRJ0032 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0032"
ms.assetid: bc6acbea-4041-4237-8b5a-f0434705d89f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# プロジェクト ビルド エラー PRJ0032
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロジェクト レベルのカスタム ビルド ステップに関する \[出力ファイル\] プロパティには、'macro\_expansion' に評価を出す 'macro' が含まれていました。  
  
 プロジェクトのカスタム ビルド ステップで、マクロ評価の問題と思われる原因により、不正な出力が生成されました。  このエラーは、ファイル パスとして不正な文字または文字の組み合わせが含まれているためにパスの書式が正しくない場合にも発生します。  
  
 このエラーを解決するには、マクロを修正するか、有効なパスを指定してください。  パスには、プロジェクト ディレクトリからの絶対パスを指定する必要があります。