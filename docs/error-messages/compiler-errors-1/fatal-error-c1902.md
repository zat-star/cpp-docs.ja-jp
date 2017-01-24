---
title: "致命的なエラー C1902 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1902"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1902"
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 致命的なエラー C1902
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プログラム データベース マネージャーが一致していません。セットアップが正しく行われているか確認してください。  
  
 プログラム データベース ファイル \(.pdb\) はと mspdb*XX*.dll の新しいバージョンを使用するシステムで見つかったコンパイラで作成されています。  このエラーは、通常、mspdbsrv.exe または mspdbcore.dll が欠落しているか、mspdb*XX*.dll と異なるバージョンがあることを示します。\(各製品のリリースを使用して mspdb の*XX*の .dll ファイル変更の *XX* の区切り記号。  たとえば、[!INCLUDE[vsprvslong](../../error-messages/compiler-errors-1/includes/vsprvslong_md.md)] ではこのファイル名は mspdb80.dll です。  
  
 mspdbsrv.exe、mspdbcore.dll、および mspdb*XX*の .dll を一致バージョンがシステムにインストールされています。  対象プラットフォーム用のコンパイラおよびリンク ツールが存在するディレクトリに一致しないバージョンがコピーされていないことを確認してください。  たとえば、これらのファイルをコピーして、適切な **PATH** 環境変数を設定せずにコマンド プロンプトからコンパイラやリンク ツールを起動できるようにした場合などについて確認します。