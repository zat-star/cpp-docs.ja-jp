---
title: "日付と時刻 | Microsoft Docs"
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
  - "日付, MFC"
  - "MFC, 日付と時刻"
  - "時間"
  - "時間, MFC プログラミング"
ms.assetid: ecf56dc5-d418-4603-ad3e-af7e205a6403
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 日付と時刻
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC は、日付と時刻を操作するさまざまな方法をサポートします。  以下に例を示します。  
  
-   汎用の時間のクラス。  [CTime](../Topic/CTime%20Class.md) と [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md) のクラスは TIME.H.で宣言された ANSI 標準時間のライブラリに関連付けられた機能のほとんどをカプセル化します。  
  
-   システム時計のサポート。  MFC のバージョン 3.0 では、Win32 `SYSTEMTIME` と `FILETIME` のデータ型の `CTime` に追加されました。  
  
-   オートメーション [日付のデータ型](../Topic/DATE%20Type.md)のサポート。  **date** のサポートは、日付\/時刻値日付を特定し、タイムアウトします。  [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) と [COleDateTimeSpan](../Topic/COleDateTimeSpan%20Class.md) のクラスは、この機能をカプセル化します。  これらは、オートメーションを使用して [COleVariant](../mfc/reference/colevariant-class.md) クラスを使用します。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [日付と時刻: 汎用的なクラス](../atl-mfc-shared/date-and-time-general-purpose-classes.md)  
  
-   [日付と時刻: SYSTEMTIME のサポート](../atl-mfc-shared/date-and-time-systemtime-support.md)  
  
-   [日付と時刻: オートメーションのサポート](../Topic/Date%20and%20Time:%20Automation%20Support.md)  
  
-   [日付と時刻: データベース サポート](../atl-mfc-shared/date-and-time-database-support.md)  
  
## 参照  
 [概念](../mfc/mfc-concepts.md)   
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)