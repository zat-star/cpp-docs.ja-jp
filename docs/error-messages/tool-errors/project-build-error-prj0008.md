---
title: "プロジェクト ビルド エラー PRJ0008 | Microsoft Docs"
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
  - "PRJ0008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0008"
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# プロジェクト ビルド エラー PRJ0008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイル 'file' を削除できませんでした。  
  
 **ファイルが別のプロセスによって開かれていないこと、また書き込み禁止になっていないことを確認してください。**  
  
 リビルドまたはクリーンアップ中に、認識されたビルド用の中間ファイルと出力ファイル、および [&#91;構成プロパティ&#93; フォルダーの &#91;全般&#93; プロパティ ページ](../Topic/General%20Property%20Page%20\(Project\).md)の \[消去時に削除する拡張子\] プロパティで指定したワイルドカードと一致するファイルが、Visual C\+\+ によってすべて削除されます。  
  
 このエラーが発生するのは、Visual C\+\+ がファイルを削除できない場合です。  このエラーを解決するには、ユーザーがビルドを実行できるように、ファイルとそのディレクトリを書き込み可能に指定してください。