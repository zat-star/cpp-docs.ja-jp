---
title: "経過時間 : オートメーション クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "追加 (日付を)"
  - "オートメーション クラス, 経過時間"
  - "計算 (日付と時刻を)"
  - "計算, 日付と時刻"
  - "日付, 計算 (間隔の)"
  - "経過時間, 計算 (オートメーションで)"
  - "間隔, 日付と時刻"
  - "時間, 経過"
ms.assetid: 26b34b37-c10e-4b91-82c3-1dc5ffb5361f
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 経過時間 : オートメーション クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

この手順では `CTime` の 2 種類のオブジェクトの間の相違点を計算し `CTimeSpan` の結果を取得する方法を示します。  
  
#### 経過時間を計算します。  
  
1.  `COleDateTime` の 2 種類のオブジェクトを作成します。  
  
2.  現在時刻への `COleDateTime` のオブジェクトのいずれかを 1 に設定します。  
  
3.  時間のかかるタスクを実行します。  
  
4.  現在時刻への `COleDateTime` のオブジェクトを設定します。  
  
5.  2 との差を実行します。  
  
     [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/CPP/elapsed-time-automation-classes_1.cpp)]  
  
## 参照  
 [日付と時刻 : オートメーションのサポート](../Topic/Date%20and%20Time:%20Automation%20Support.md)