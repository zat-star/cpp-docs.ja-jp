---
title: "CFileTime クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CFileTime"
  - "CFileTime"
  - "ATL.CFileTime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFileTime クラス"
  - "共有クラス, CFileTime"
ms.assetid: 1a358a65-1383-4124-b0d4-59b026e6860f
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CFileTime クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、ファイルに関連付けられた日付と時刻の値を管理するためのメソッドを提供します。  
  
## 構文  
  
```  
  
   class CFileTime :   
public FILETIME  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CFileTime::CFileTime](../Topic/CFileTime::CFileTime.md)|コンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CFileTime::GetCurrentTime](../Topic/CFileTime::GetCurrentTime.md)|現在のシステム日付と時刻を表す `CFileTime` のオブジェクトを取得するには、この静的関数を呼び出します。|  
|[CFileTime::GetTime](../Topic/CFileTime::GetTime.md)|`CFileTime` のオブジェクトから時刻を取得するときにこのメソッドを呼び出します。|  
|[CFileTime::LocalToUTC](../Topic/CFileTime::LocalToUTC.md)|世界協定時刻 \(UTC\) \(UTC\) に基づいてファイルの時刻にローカル ファイルの時刻を変換するには、このメソッドを呼び出します。|  
|[CFileTime::SetTime](../Topic/CFileTime::SetTime.md)|`CFileTime` のオブジェクトに格納されている時刻を設定するには、このメソッドを呼び出します。|  
|[CFileTime::UTCToLocal](../Topic/CFileTime::UTCToLocal.md)|ローカル ファイルの日時に \(UTC\) に基づいて世界協定時刻 \(UTC 時刻に変換するには、このメソッドを呼び出します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CFileTime::operator \-](../Topic/CFileTime::operator%20-.md)|この演算子が `CFileTime` または `CFileTimeSpan` のオブジェクトの減算を実行するために使用されます。|  
|[CFileTime::operator \!\=](../Topic/CFileTime::operator%20!=.md)|この演算子は非等値の `CFileTime` の 2 種類のオブジェクトを比較します。|  
|[CFileTime::operator \+](../Topic/CFileTime::operator%20+.md)|この演算子が `CFileTimeSpan` オブジェクトの追加を実行するために使用されます。|  
|[CFileTime::operator \+\=](../Topic/CFileTime::operator%20+=.md)|この演算子が `CFileTimeSpan` オブジェクトの追加を実行し、現在の結果をオブジェクトに割り当てるために使用されます。|  
|[CFileTime::operator \<](../Topic/CFileTime::operator%20%3C.md)|この演算子は、小さいかを確認するに `CFileTime` の 2 種類のオブジェクトを比較します。|  
|[CFileTime::operator \<\=](../Topic/CFileTime::operator%20%3C=.md)|この演算子は、または小さいかを確認するに `CFileTime` の 2 種類のオブジェクトを比較します。|  
|[CFileTime::operator \=](../Topic/CFileTime::operator%20=.md)|代入演算子です。|  
|[CFileTime::operator \-\=](../Topic/CFileTime::operator%20-=.md)|この演算子が `CFileTimeSpan` のオブジェクトの減算を実行し、現在の結果をオブジェクトに割り当てるために使用されます。|  
|[CFileTime::operator \=\=](../Topic/CFileTime::operator%20==.md)|この演算子は、の `CFileTime` の 2 種類のオブジェクトを比較します。|  
|[CFileTime::operator \>](../Topic/CFileTime::operator%20%3E.md)|この演算子は、より大きなを確認します。`CFileTime` の 2 種類のオブジェクトを比較します。|  
|[CFileTime::operator \>\=](../Topic/CFileTime::operator%20%3E=.md)|この演算子は、より大きいかを確認します。`CFileTime` の 2 種類のオブジェクトを比較します。|  
  
### パブリック定数  
  
|名前|説明|  
|--------|--------|  
|[CFileTime::Day](../Topic/CFileTime::Day.md)|1 日を構成する 100 ナノ秒の間隔の数を格納する静的データ メンバー。|  
|[CFileTime::Hour](../Topic/CFileTime::Hour.md)|1 時間を構成する 100 ナノ秒の間隔の数を格納する静的データ メンバー。|  
|[CFileTime::Millisecond](../Topic/CFileTime::Millisecond.md)|1 ミリ秒を構成する 100 ナノ秒の間隔の数を格納する静的データ メンバー。|  
|[CFileTime::Minute](../Topic/CFileTime::Minute.md)|1 分を構成する 100 ナノ秒の間隔の数を格納する静的データ メンバー。|  
|[CFileTime::Second](../Topic/CFileTime::Second.md)|1 秒を構成する 100 ナノ秒の間隔の数を格納する静的データ メンバー。|  
|[CFileTime::Week](../Topic/CFileTime::Week.md)|1 週間を構成する 100 ナノ秒の間隔の数を格納する静的データ メンバー。|  
  
## 解説  
 このクラスは、ファイルの作成、および変更に関連付けられた日付と時刻の値を管理するためのメソッドを提供します。  このクラスのメソッドとデータは、相対時刻の値を処理 `CFileTimeSpan` のオブジェクトとともによく使用されます。  
  
 日付と時刻の値は 1601、1 年 1 月 1 日以降の 100 ナノ秒の間隔の数を表す 64 ビット値として格納されます。  これは、UTC の \(UTC\) の形式です。  
  
 次のスタティック const のメンバー変数は、計算を簡単にするために用意されています:  
  
|メンバー変数|100 ナノ秒の間隔の数|  
|------------|------------------|  
|Millisecond|10,000|  
|解決します。|ミリ秒\* 1,000|  
|分|秒に\* 60|  
|時間|分\* 60|  
|日|時間\* 24|  
|週|\* 7 日|  
  
 **Note** は、すべてのファイル システム レコードの作成と最終アクセス日時、およびすべてのファイル システムそれらを記録することはできません。  たとえば、Windows NT の FAT ファイル システムで、時間を持つ 10 ミリ秒の解決を作成し、書き込み時間が 2 秒の解決があり、アクセス時間に 1 日 \(アクセス日\) の解決があります。  NTFS で、アクセス時間が 1 時間の解決があります。  さらに、UTC のディスクの現地時刻、NTFS の記録のディスクのタイム FAT の記録。タイム  詳細については、[ファイルの時間](http://msdn.microsoft.com/library/windows/desktop/ms724290)を参照してください。  
  
## 継承階層  
 `FILETIME`  
  
 `CFileTime`  
  
## 必要条件  
 **ヘッダー :** atltime.h  
  
## 参照  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [CFileTimeSpan クラス](../../atl-mfc-shared/reference/cfiletimespan-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC の共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)