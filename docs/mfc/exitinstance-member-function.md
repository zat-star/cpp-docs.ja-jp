---
title: "ExitInstance メンバー関数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CWinApp::ExitInstance"
  - "CWinApp.ExitInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinApp クラス, ExitInstance"
  - "ExitInstance メソッド"
  - "プログラム [C++], 終了"
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ExitInstance メンバー関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラス [CWinApp](../mfc/reference/cwinapp-class.md) の [ExitInstance](../Topic/CWinApp::ExitInstance.md) のメンバー関数は、アプリケーションを終了するユーザーの結果としてアプリケーションのコピーが完了するたびに、通常呼び出されます。  
  
 処理する特別なクリーンアップが必要な場合は、グラフィック デバイス インターフェイス \(GDI\) のリソースを解放するか、またはプログラムの実行中に使用されたメモリを解放するなどの `ExitInstance` をオーバーライドします。  ただし、ドキュメントとビューなどの標準項目のクリーンアップはそれらのオブジェクトに特別なクリーンアップの仕様をする他のオーバーライドできるな関数をフレームワークによって提供されます。  
  
## 参照  
 [CWinApp : アプリケーション クラス](../Topic/CWinApp:%20The%20Application%20Class.md)