---
title: "プロジェクト ビルド エラー PRJ0006 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0006"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0006"
ms.assetid: ce092be4-1652-414f-8cb5-b97ef5841f89
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# プロジェクト ビルド エラー PRJ0006
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

一時ファイル 'file' を開けませんでした。ファイルが存在し、ディレクトリが書き込み禁止になっていないことを確認してください。  
  
 Visual C\+\+ でビルド処理中に一時ファイルを作成できませんでした。  このエラーには以下の原因が考えられます。  
  
-   一時ディレクトリが指定されていない。  
  
-   一時ディレクトリが読み取り専用である。  
  
-   空き容量が不足している。  
  
-   $\(IntDir\) フォルダーが読み取り専用であるか、読み取り専用の一時ファイルを含んでいる。  
  
 このエラーは、"PRJ0007: 出力ディレクトリ 'directory' を作成できませんでした。" エラーの後にも発生します。  PRJ0007 エラーは、$\(IntDir\) ディレクトリを作成できなかったこと、および一時ファイルの作成も失敗することを意味します。  
  
 一時ファイルは、以下の項目を指定すると必ず作成されます。  
  
-   応答ファイル  
  
-   カスタム ビルド ステップ  
  
-   ビルド イベント