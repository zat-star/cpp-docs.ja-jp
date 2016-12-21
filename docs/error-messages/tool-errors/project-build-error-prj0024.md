---
title: "プロジェクト ビルド エラー PRJ0024 | Microsoft Docs"
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
  - "PRJ0024"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0024"
ms.assetid: 8bde6368-6c1b-4e04-bc5e-3c6d0b8fa1d7
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# プロジェクト ビルド エラー PRJ0024
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unicode のパス 'path' をユーザーの ANSI コード ページに変換できませんでした。  
  
 ***path***  はパス文字列の元の Unicode バージョンです。  このエラーは、現在のシステム コード ページ用の ANSI に直接変換できない Unicode パスがある場合に発生する可能性があります。  
  
 また、コンピューターに存在しないコード ページを使用して、システムで開発されたプロジェクトを操作する場合にも発生する可能性があります。  
  
 このエラーを解決するには、ANSI テキストを使用するようにパスを更新するか、コンピューターにコード ページをインストールしてシステムを既定の設定にしてください。