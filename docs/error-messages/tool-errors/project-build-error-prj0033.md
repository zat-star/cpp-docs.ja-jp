---
title: "プロジェクト ビルド エラー PRJ0033 | Microsoft Docs"
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
  - "PRJ0033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0033"
ms.assetid: 84d4a052-0586-4b78-9315-81c1e8386c1e
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# プロジェクト ビルド エラー PRJ0033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイル 'file' のカスタム ビルド ステップに関する \[追加の依存関係\] プロパティには、'macro\_expansion' に評価を出す 'macro' が含まれていました。  
  
 ファイルのカスタム ビルド ステップで、マクロ評価の問題が原因と思われるエラーが、その他の依存関係で見つかりました。  このエラーは、ファイル パスとして不正な文字または文字の組み合わせが含まれているためにパスの書式が正しくない場合にも発生します。  
  
 このエラーを解決するには、マクロを修正するか、有効なパスを指定してください。  パスには、プロジェクト ディレクトリからの絶対パスを指定する必要があります。