---
title: "BSCMAKE エラー BK1513 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "BK1513"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1513"
ms.assetid: 9ba87c09-8d82-4c80-b0cf-a8de63dcf9da
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# BSCMAKE エラー BK1513
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

インクリメンタルでないビルドにはすべての .SBR ファイルが必要です。  
  
 1 つ以上の .sbr ファイルが切り捨てられたため、BSCMAKE では、新しいブラウザー情報 \(.bsc\) ファイルをビルドできません。  切り捨てられた .sbr ファイルの名前を見つけるには、このエラーに伴う [BK4502](../../error-messages/tool-errors/bscmake-warning-bk4502.md) 警告を読みます。  
  
 BSCMAKE では .bsc ファイルを切り捨てられた .sbr ファイルで更新できますが、新しいものをビルドすることはできません。  BSCMAKE では、次の理由で新しい .bsc ファイルをビルドする可能性があります。  
  
-   .bsc ファイルが欠落しています。  
  
-   .bsc ファイルに指定されたファイル名が間違っています。  
  
-   .bsc ファイルが破損しています。  
  
 この問題を解決するには、切り捨てられた .sbr ファイルを削除して再ビルドするか、または、ソリューションをクリーンして再ビルドします。  \(IDE で、**\[ビルド\]**、**\[ソリューションのクリーン\]**、**\[ビルド\]**、**\[ソリューションのリビルド\]** の順に選択します。\)