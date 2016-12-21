---
title: "日付と時刻 : 汎用クラス | Microsoft Docs"
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
  - "日付と時刻クラス"
  - "時刻クラス"
ms.assetid: b8115d7f-428a-4c41-9970-18502f2caca2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 日付と時刻 : 汎用クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、現在までに関連するクラス ライブラリの汎用サービスとタイム マネージャーを使用する方法について説明します。  説明されている手順は次のとおりです。:  
  
-   [現在時刻を取得できます。](../atl-mfc-shared/current-time-general-purpose-classes.md)  
  
-   [経過時間の計算](../atl-mfc-shared/elapsed-time-general-purpose-classes.md)  
  
-   [日付と時刻の文字列形式を指定できます。](../atl-mfc-shared/formatting-time-values-general-purpose-classes.md)  
  
 `CTime` のクラスは、日付と時刻の情報を簡単に表す方法を提供します。  `CTimeSpan` のクラスは `CTime` の 2 種類のオブジェクトの違いなどの経過時間を表します。  
  
> [!NOTE]
>  CTime のオブジェクトが 1970 年 1 月 1 日 1、2038 年 1 月 1 日 18 時の日付を表すことができます。  `CTime` のオブジェクトに 1 第 2 の解決があります。  `CTime` は、" *ランタイム ライブラリ*リファレンスで定義されている `time_t` のデータ型に基づいています。  
  
## 参照  
 [日付と時刻](../atl-mfc-shared/date-and-time.md)