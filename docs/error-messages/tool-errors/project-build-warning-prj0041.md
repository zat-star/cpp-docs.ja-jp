---
title: "プロジェクト ビルドの警告 PRJ0041 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0041"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0041"
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# プロジェクト ビルドの警告 PRJ0041
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

依存関係 'dependency' \(ファイル 'file'\) が見つかりません。プロジェクトをビルドすることはできますが、このファイルが見つかるまでプロジェクトは最新バージョンとはなりません。  
  
 ファイル \(リソース ファイルや .idl\/.odl ファイルなど\) に、プロジェクト システムが解決できない include ステートメントが含まれていました。  
  
 プロジェクト システムはプリプロセッサ ステートメント \(\#if など\) を処理しないため、問題となっているステートメントは、実際にはビルドの一部でない可能性があります。  
  
 この警告を解決するには、.rc ファイルで不要なコードをすべて削除するか、適切な名前のプレースホルダー ファイルを追加します。