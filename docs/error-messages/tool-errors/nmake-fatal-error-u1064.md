---
title: "NMAKE の致命的なエラー U1064 | Microsoft Docs"
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
  - "U1064"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1064"
ms.assetid: 7141e66e-cde6-4173-84df-a391f3ebcdd1
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE の致命的なエラー U1064
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MAKEFILE が見つかりません、またターゲットが指定されていません。  
  
 NMAKE のコマンド ラインにはメイクファイルもターゲットも指定されておらず、現在のフォルダーにも MAKEFILE という名前のファイルは存在しません。  
  
 NMAKE には、メイクファイルまたはコマンド ラインのターゲット \(あるいはその両方\) を指定する必要があります。  メイクファイルを NMAKE で使用するには、\/F オプションを指定するかメイクファイルに MAKEFILE という名前を付けて現在のフォルダーに置いてください。  メイクファイルが用意されていない場合でも、コマンド ラインでターゲットを指定していれば NMAKE は推論規則に基づいてターゲットを生成します。