---
title: "ファイルの状態の操作 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "例 [MFC], ファイルの状態"
  - "ファイルの状態 [C++]"
  - "ファイル [C++], アクセス"
  - "ファイル [C++], ステータス情報"
  - "ステータス (ファイルの)"
ms.assetid: 1b8891d6-eb0f-4037-a837-4928fe595222
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ファイルの状態の操作
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CFile` は、取得するファイルの状態、ファイルがあるかどうかを設定する方法、および作成変更日と、論理サイズとパスをサポートします。  
  
### ファイルに状態を取得します。  
  
1.  ファイルに関する情報を取得したり、設定に [CFile](../mfc/reference/cfile-class.md) クラスを使用します。  1 個の役に立つのは、ファイルが存在するかどうかを判断するために `CFile` の静的メンバー関数 **GetStatus** を使用します。  **GetStatus** が、指定されたファイルが見つからない場合は 0 を返します。  
  
 したがって **CFile::modeCreate** を使用するファイルを、次の例に示すように開くと、かどうかフラグを判断するために **GetStatus** の結果を使用する:  
  
 [!code-cpp[NVC_MFCFiles#3](../mfc/codesnippet/CPP/accessing-file-status_1.cpp)]  
  
 関連情報については、[シリアル化](../Topic/Serialization%20in%20MFC.md)を参照してください。  
  
## 参照  
 [ファイル](../mfc/files-in-mfc.md)