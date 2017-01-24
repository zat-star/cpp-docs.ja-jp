---
title: "ML Fatal Error A1017 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A1017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1017"
ms.assetid: bef0b312-5431-4e5a-b637-c19919acf01b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ML Fatal Error A1017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**ソース ファイル名。**  
  
 ML はリンカーにアセンブルしたり渡すようにファイルが見つかりませんでした。  
  
 このエラーは動作にファイル名を指定しないで ML のコマンド ライン オプションを与える場合に生成されます。  一つの拡張子のないファイルをアセンブルするには**\/Ta** のコマンド ライン オプションを使用します。  
  
 このエラーはパラメーターなしの ML によって ML の環境変数がコマンド ライン オプションを指定すると生成できます。  
  
## 参照  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)