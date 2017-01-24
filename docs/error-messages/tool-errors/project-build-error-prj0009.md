---
title: "プロジェクト ビルド エラー PRJ0009 | Microsoft Docs"
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
  - "PRJ0009"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0009"
ms.assetid: 89291778-cda4-495d-983f-ddcc06dfc98b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# プロジェクト ビルド エラー PRJ0009
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ビルド ログを開いて書き込むことができませんでした。  
  
 **ファイルが別のプロセスによって開かれていないこと、また書き込み禁止になっていないことを確認してください。**  
  
 \[ビルドのログ\] プロパティを **\[はい\]** に設定してビルドまたはリビルドを実行した後に、Visual C\+\+ でビルド ログを排他モードで開くことができませんでした。  
  
 \[ビルドのログ\] の設定を調べるには、\[ツール\] メニューの **\[オプション\]** をクリックして **\[オプション\]** ダイアログ ボックスを開き、\[プロジェクト\] フォルダーの \[VC\+\+ ビルド\] を選択します。  ビルド ファイルの名前は BuildLog.htm であり、中間ディレクトリ $\(IntDir\) に書き込まれます。  
  
 このエラーには以下の原因が考えられます。  
  
-   Visual C\+\+ の 2 つのプロセスを実行しているときに、同時に両方で同じプロジェクトの同じ構成のビルドを実行しようとしている。  
  
-   ビルド ログ ファイルをロックしているプロセスでファイルを開いている。  
  
-   ファイルの作成に必要なアクセス許可がない。  
  
-   現在のユーザーが、BuildLog.htm ファイルへの書き込みアクセス権を持っていない。