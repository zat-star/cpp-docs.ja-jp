---
title: "プロジェクト ビルド エラー PRJ0002 | Microsoft Docs"
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
  - "PRJ0002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0002"
ms.assetid: 1c820b1f-9a24-4681-80ed-4fcbfd7caa00
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# プロジェクト ビルド エラー PRJ0002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

エラーの結果が 'command line' より返されました。  
  
 **\[プロパティ ページ\]** ダイアログ ボックスへのユーザーの入力によって生成されたコマンド ***command line*** からエラー コードが返されましたが、\[出力\] ウィンドウに情報が表示されません。  
  
 このエラーの解決方法は、エラーを生成したツールによって異なります。  MIDL の場合は、\/o \(出力のリダイレクト\) を定義していれば、エラーの場所を確認できます。  
  
 カスタム ビルド ステップやビルド イベントなど、エラー条件の情報を含まないバッチ ファイルも、このエラーの原因となることがあります。