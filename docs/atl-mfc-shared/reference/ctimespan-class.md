---
title: "CTimeSpan クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CTimeSpan"
  - "CTimeSpan"
  - "timespan"
  - "ATL::CTimeSpan"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTimeSpan クラス"
  - "経過時間, CTimeSpan オブジェクト"
  - "共有クラス, CTimeSpan"
  - "期間"
  - "時間, 経過"
  - "期間"
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CTimeSpan クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

時間の秒数として内部的に格納された時間。  
  
## 構文  
  
```  
class CTimeSpan  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CTimeSpan::CTimeSpan](../Topic/CTimeSpan::CTimeSpan.md)|さまざまな方法で `CTimeSpan` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CTimeSpan::Format](../Topic/CTimeSpan::Format.md)|書式指定された文字列に `CTimeSpan` を変換します。|  
|[CTimeSpan::GetDays](../Topic/CTimeSpan::GetDays.md)|この `CTimeSpan`の完全な日数を表す値を返します。|  
|[CTimeSpan::GetHours](../Topic/CTimeSpan::GetHours.md)|現在の曜日時間数を表す値を返します \(– 23 ~ 23\)。|  
|[CTimeSpan::GetMinutes](../Topic/CTimeSpan::GetMinutes.md)|現在の時間を分単位で表す値を返します \(– 59 ~ 59\)。|  
|[CTimeSpan::GetSeconds](../Topic/CTimeSpan::GetSeconds.md)|現在の時刻の秒数を表す値を返します \(– 59 ~ 59\)。|  
|[CTimeSpan::GetTimeSpan](../Topic/CTimeSpan::GetTimeSpan.md)|`CTimeSpan` オブジェクトの値を返します。|  
|[CTimeSpan::GetTotalHours](../Topic/CTimeSpan::GetTotalHours.md)|この `CTimeSpan`の完全な時間数を表す値を返します。|  
|[CTimeSpan::GetTotalMinutes](../Topic/CTimeSpan::GetTotalMinutes.md)|この `CTimeSpan`の完全な分の総数を表す値を返します。|  
|[CTimeSpan::GetTotalSeconds](../Topic/CTimeSpan::GetTotalSeconds.md)|この `CTimeSpan`の完全な秒の総数を表す値を返します。|  
|[CTimeSpan::Serialize64](../Topic/CTimeSpan::Serialize64.md)|アーカイブにデータをシリアル化したり、アーカイブからデータをシリアル化したりします。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator \+ –](../Topic/CTimeSpan::operator%20+,%20-.md)|`CTimeSpan` のオブジェクトを加算します。|  
|[– \= 演算子 \+\=](../Topic/CTimeSpan::operator%20+=,%20-=.md)|この `CTimeSpan`との間で `CTimeSpan` のオブジェクトを加算します。|  
|[演算子 \=\= \< など.](../Topic/CTimeSpan%20Comparison%20Operators.md)|2 種類の相対的な時刻の値を比較します。|  
  
## 解説  
 `CTimeSpan` には、基本クラスはありません。  
  
 `CTimeSpan` 関数は、日、時、分、および秒のさまざまな組み合わせ\) をに変換します。  
  
 `CTimeSpan` のオブジェクトは、8 バイトである **\_\_time64\_t** の構造体に格納されます。  
  
 コンパニオン クラス、[CTime](../Topic/CTime%20Class.md)は、絶対時刻を表します。  
  
 `CTime` クラスと `CTimeSpan` クラスは、派生クラスを生成するようにはデザインされていません。  仮想関数がないため、`CTime` と `CTimeSpan` の両方のオブジェクトのサイズは厳密に 8 バイトです。  ほとんどのメンバー関数はインライン関数になります。  
  
 `CTimeSpan`の使用の詳細については、" " [&#91;日付と時刻&#93;](../../atl-mfc-shared/date-and-time.md)、および *ランタイム ライブラリ リファレンスの*[時間管理](../../c-runtime-library/time-management.md) を参照してください。  
  
## 必要条件  
 **Header:** atltime.h  
  
## 参照  
 [asctime、\_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [\_ftime、\_ftime32、\_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime、\_gmtime32、\_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime、\_localtime32、\_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [strftime、wcsftime、\_strftime\_l、\_wcsftime\_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time、\_time32、\_time64](../Topic/time,%20_time32,%20_time64.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC の共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)