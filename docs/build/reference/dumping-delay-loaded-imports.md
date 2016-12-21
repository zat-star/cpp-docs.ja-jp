---
title: "遅延読み込みしたインポートのダンプ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "遅延読み込みされたインポート"
  - "遅延読み込みされたインポート, ダンプ"
  - "インポート (遅延読み込み)"
ms.assetid: f766acf4-9df8-4b85-8cf6-0be3ffc4c124
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 遅延読み込みしたインポートのダンプ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

遅延読み込みしたインポートは、[dumpbin \/imports](../../build/reference/imports-dumpbin.md) を使用してダンプでき、標準インポートとは少し異なる情報を付けて表示されます。  各インポートは、\/imports ダンプ固有のセクションに分離され、遅延読み込みしたインポートであることを明示的に示すラベルが付けられます。  イメージにアンロード情報がある場合は、それが表示されます。  バインド情報がある場合は、ターゲット DLL の時刻\/日付スタンプとインポートのバインド アドレスが表示されます。  
  
## 参照  
 [リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)