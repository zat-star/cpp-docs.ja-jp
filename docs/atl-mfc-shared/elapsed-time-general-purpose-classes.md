---
title: "経過時間 : 汎用クラス | Microsoft Docs"
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
  - "計算 (日付と時刻を)"
  - "計算, 日付と時刻"
  - "日付, 計算 (間隔の)"
  - "経過時間"
  - "経過時間, 計算"
  - "間隔, 日付と時刻"
  - "時間, 経過"
ms.assetid: e5c5d3d2-ce1d-409e-875c-98848434e716
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 経過時間 : 汎用クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の手順では `CTime` の 2 種類のオブジェクトの間の相違点を計算し `CTimeSpan` の結果を取得する方法を示します。  
  
#### 経過時間を計算します。  
  
1.  次のように経過時間を計算するために `CTime` と `CTimeSpan` のオブジェクトの使用:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#174](../atl-mfc-shared/codesnippet/CPP/elapsed-time-general-purpose-classes_1.cpp)]  
  
     `elapsedTime`を計算して、経過時間の値コンポーネントを配置するために `CTimeSpan` のメンバー関数を使用できます。  
  
## 参照  
 [日付と時刻 : 汎用クラス](../atl-mfc-shared/date-and-time-general-purpose-classes.md)