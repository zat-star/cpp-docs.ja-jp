---
title: "コンパイラの警告 (レベル 1) C4819 | Microsoft Docs"
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
  - "C4819"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4819"
ms.assetid: c0316e85-249c-414d-9df0-622d077c6bc2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4819
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルは、現在のコード ページ \(数\) で表示できない文字を含んでいます。データの損失を防ぐために、ファイルを Unicode 形式で保存してください。  
  
 C4819 は、ANSI ソース ファイルが、ファイル内のすべての文字を表現できないコードページを使用するシステムでコンパイルされたときに発生します。  
  
 C4819 を解決するには、ファイルを Unicode 形式で保存します。  Visual Studio で **\[ファイル\]**、**\[保存オプションの詳細設定\]** の順に選択します。  **\[保存オプションの詳細設定\]** ダイアログ ボックスで、ファイルのすべての文字を表現できるエンコード、たとえば、UTF\-8 を選択し、**\[OK\]** を選択します。