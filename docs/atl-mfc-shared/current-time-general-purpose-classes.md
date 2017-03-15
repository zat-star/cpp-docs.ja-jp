---
title: "現在の時刻 : 汎用クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "現在時刻, CTime オブジェクト"
  - "初期化 (オブジェクトを), 現在の時刻で"
  - "プロシージャ, 取得 (現在の時刻を)"
  - "時間, 取得 (現在の)"
  - "時間, 設定 (現在)"
ms.assetid: c39e6775-6a92-4b27-95a7-5c86ed371d8a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 現在の時刻 : 汎用クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の手順では `CTime` のオブジェクトを作成し、現在時刻で初期化する方法を示します。  
  
#### 現在時刻を取得する  
  
1.  次のように、`CTime` のオブジェクトを代入します:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#171](../atl-mfc-shared/codesnippet/CPP/current-time-general-purpose-classes_1.cpp)]  
  
    > [!NOTE]
    >  有効な時刻への `CTime` の初期化されていないオブジェクトは初期化されません。  
  
2.  オペレーティング システムから現在の時刻を取得するに `CTime::GetCurrentTime` 関数を呼び出します。  この関数は `CTime`の値の設定に使用できる `CTime` のオブジェクトを次のように返します:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#172](../atl-mfc-shared/codesnippet/CPP/current-time-general-purpose-classes_2.cpp)]  
  
     `GetCurrentTime` が `CTime` クラスの静的メンバー関数であるため、クラスとスコープ解決演算子 \(`::`\) の名前を、`CTime::GetCurrentTime()`修飾する必要があります。  
  
 もちろん、前に説明した 2 ステップは、一つのプログラム文に次のように結合できます:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#173](../atl-mfc-shared/codesnippet/CPP/current-time-general-purpose-classes_3.cpp)]  
  
## 参照  
 [日付と時刻 : 汎用クラス](../atl-mfc-shared/date-and-time-general-purpose-classes.md)