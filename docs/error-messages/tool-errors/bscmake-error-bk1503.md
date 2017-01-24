---
title: "BSCMAKE エラー BK1503 | Microsoft Docs"
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
  - "BK1503"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1503"
ms.assetid: e6582344-b91e-486f-baf3-4f9028d83c3b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# BSCMAKE エラー BK1503
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイル 'ファイル名' に書き込めません。\[: 理由\]  
  
 BSCMAKE では、コンパイル時に生成された .sbr ファイルが、1 つのブラウザー データベースに結合されます。  作成されたブラウザー データベースのサイズが 64 MB を超えた場合や、入力ファイル \(.sbr ファイル\) の数が 4092 個を超えた場合に、このエラーが表示されます。  
  
 .sbr ファイルの数が 4092 個よりも多い場合は、入力ファイルの数を減らす必要があります。  Visual Studio 開発環境で、プロジェクト全体に [\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) オプションを指定してから、ファイルを 1 つずつ再確認してください。  
  
 .bsc ファイルのサイズが 64 MB を超える場合は、入力ファイルである .sbr ファイルの数を減らすことで、生成される .bsc ファイルのサイズを小さくできます。  また、\/Em \(マクロ展開シンボルを除外する\)、\/El \(ローカル変数を除外する\)、\/Es \(システム インクルード ファイルを除外する\) の各オプションを指定することによっても、ブラウザー情報ファイルのサイズを小さくできます。  
  
## 参照  
 [BSCMAKE オプション](../Topic/BSCMAKE%20Options.md)