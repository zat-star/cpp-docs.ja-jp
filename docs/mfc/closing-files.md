---
title: "ファイルを閉じる | Microsoft Docs"
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
  - "ファイル [C++], 閉じる"
  - "MFC [C++], ファイルの操作"
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ファイルを閉じる
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ファイル I\/O 操作を終了する通常どおりに、メッセージ ボックスを閉じる必要があります。  
  
#### ファイルを閉じます。  
  
1.  **閉じる** メンバー関数を使用します。  この関数はファイル システム ファイルを閉じ、必要に応じてバッファーをフラッシュします。  
  
 フレームの [CFile](../mfc/reference/cfile-class.md) オブジェクト \(この例で [ファイルを開いているとき](../Topic/Opening%20Files.md)割り当てたら\) に表示される、オブジェクトは自動的に終了し、スコープ外に出たまたは破棄します。  `CFile` オブジェクトを削除しても、削除しないファイル システム内の物理ファイルを確認します。  
  
## 参照  
 [ファイル](../mfc/files-in-mfc.md)