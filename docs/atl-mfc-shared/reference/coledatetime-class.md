---
title: "COleDateTime クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDateTime"
  - "ATL.COleDateTime"
  - "ATL::COleDateTime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDateTime クラス"
  - "Date データ型, MFC のカプセル化"
  - "日付, 処理 (MFC での)"
  - "共有クラス, COleDateTime"
  - "時間, 処理 (MFC での)"
  - "時刻のみの値"
ms.assetid: e718f294-16ec-4649-88b6-a4dbae5178fb
caps.latest.revision: 34
caps.handback.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDateTime クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE オートメーションで使用される `DATE` データ型をカプセル化します。  
  
## 構文  
  
```  
class COleDateTime  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleDateTime::COleDateTime](../Topic/COleDateTime::COleDateTime.md)|`COleDateTime` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleDateTime::Format](../Topic/COleDateTime::Format.md)|`COleDateTime` オブジェクトの書式化された文字列表現を生成します。|  
|[COleDateTime::GetAsDBTIMESTAMP](../Topic/COleDateTime::GetAsDBTIMESTAMP.md)|**DBTIMESTAMP** のデータ構造体として `COleDateTime` のオブジェクトの時刻を取得するときにこのメソッドを呼び出します。|  
|[COleDateTime::GetAsSystemTime](../Topic/COleDateTime::GetAsSystemTime.md)|[SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) のデータ構造体として `COleDateTime` のオブジェクトの時刻を取得するときにこのメソッドを呼び出します。|  
|[COleDateTime::GetAsUDATE](../Topic/COleDateTime::GetAsUDATE.md)|**UDATE** のデータ構造体として `COleDateTime` の時間を取得するときにこのメソッドを呼び出します。|  
|[COleDateTime::GetCurrentTime](../Topic/COleDateTime::GetCurrentTime.md)|現在時刻を表す `COleDateTime` オブジェクトを構築します \(静的メンバー関数\)。|  
|[COleDateTime::GetDay](../Topic/COleDateTime::GetDay.md)|このオブジェクトが表す `COleDateTime` の日付を返します \(1 – 31\)。|  
|[COleDateTime::GetDayOfWeek](../Topic/COleDateTime::GetDayOfWeek.md)|`COleDateTime` のこのオブジェクトが表す曜日を返します \(日曜日\= 1\)。|  
|[COleDateTime::GetDayOfYear](../Topic/COleDateTime::GetDayOfYear.md)|`COleDateTime` のこのオブジェクトが表す年の日付を返します \(1年1月1日\= 1日\)。|  
|[COleDateTime::GetHour](../Topic/COleDateTime::GetHour.md)|`COleDateTime` のこのオブジェクトが表す時間を返します \(0 – 23\)。|  
|[COleDateTime::GetMinute](../Topic/COleDateTime::GetMinute.md)|`COleDateTime` のこのオブジェクトが表す分を返します \(0 – 59\)。|  
|[COleDateTime::GetMonth](../Topic/COleDateTime::GetMonth.md)|`COleDateTime` のこのオブジェクトが表すを返します \(月1 – 12\)。|  
|[COleDateTime::GetSecond](../Topic/COleDateTime::GetSecond.md)|2番目の `COleDateTime` でこのオブジェクトを表します \(0\) 59 –返します。|  
|[COleDateTime::GetStatus](../Topic/COleDateTime::GetStatus.md)|`COleDateTime` のオブジェクトの状態 \(および\) を取得します。|  
|[COleDateTime::GetYear](../Topic/COleDateTime::GetYear.md)|`COleDateTime` のこのオブジェクトが表す年を返します。|  
|[COleDateTime::ParseDateTime](../Topic/COleDateTime::ParseDateTime.md)|文字列からの日付と時刻の値の読み取り、`COleDateTime`の値を設定します。|  
|[COleDateTime::SetDate](../Topic/COleDateTime::SetDate.md)|指定した日付だけ値への `COleDateTime` でこのオブジェクトの値を設定します。|  
|[COleDateTime::SetDateTime](../Topic/COleDateTime::SetDateTime.md)|指定した日付\/時刻値に `COleDateTime` でこのオブジェクトの値を設定します。|  
|[COleDateTime::SetStatus](../Topic/COleDateTime::SetStatus.md)|`COleDateTime` でこのオブジェクトの状態 \(有効性\) を設定します。|  
|[COleDateTime::SetTime](../Topic/COleDateTime::SetTime.md)|指定した時刻だけの値への `COleDateTime` でこのオブジェクトの値を設定します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[COleDateTime::operatorの\=\=、COleDateTime::operatorなど\<.](../Topic/COleDateTime%20Relational%20Operators.md)|`COleDateTime` の2個の値を比較します。|  
|[COleDateTime::operator \+、\- COleDateTime::operator](../Topic/COleDateTime::operator%20+,%20-.md)|`COleDateTime` の値を加算します。|  
|[COleDateTime::operator \+\=、COleDateTime::operator \- \=](../Topic/COleDateTime::operator%20+=,%20-=.md)|`COleDateTime` でこのオブジェクトから `COleDateTime` の値を加算します。|  
|[COleDateTime::operator \=](../Topic/COleDateTime::operator%20=.md)|`COleDateTime` 値をコピーします。|  
|[COleDateTime::operatorの日付、COleDateTime::operator Date\*](../Topic/COleDateTime::operator%20DATE.md)|`DATE` か `DATE*`に `COleDateTime` の値を変換します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[COleDateTime::m\_dt](../Topic/COleDateTime::m_dt.md)|`COleDateTime` のこのオブジェクトの基になる **\[date\]** が含まれます。|  
|[COleDateTime::m\_status](../Topic/COleDateTime::m_status.md)|`COleDateTime` のオブジェクトの状態が含まれます。|  
  
## 解説  
 `COleDateTime` には、基本クラスはありません。  
  
 このデータ型は、OLE オートメーションの [VARIANT](http://msdn.microsoft.com/ja-jp/e305240e-9e11-4006-98cc-26f4932d2118) データ型で使用できる型の 1 つです。  `COleDateTime` 値は、絶対日付と時刻を表します。  
  
 `DATE` 型は浮動小数点値として実装されます。  日数は 1899 年 12 月 30 日の午前 0 時から数えられます。  次の表は、いくつかの日付とそれに関連付けられた値を示しています。  
  
|日付|価値|  
|--------|--------|  
|1899 年 12 月 29 日午前 0 時|\-1.0|  
|1899 年 12 月 29 日午前 6 時|\-1.25|  
|1899 年 12 月 30 日午前 0 時|0.0|  
|1899 年 12 月 31 日午前 0 時|1.0|  
|1900年1月1日1、6 AM..|2.25|  
  
> [!CAUTION]
>  日の値が1899年1月12日の午前前に30が負になるのは、上の表のメモ、時刻の値。  たとえば、日付を表す整数が正の1899 \(12年12月30日以降の場合\) または負であるかどうか、午前6:00小数値は0.25で表されますに関係なく常に1899 \(12年12月30日より前に\)。  これは単純な浮動小数点の比較が誤って12\/29\/1899の午前6:00を表すため `COleDateTime` を1表現の午前7:00より **later** 当日並べ替えることを意味します。  
  
 `COleDateTime` クラスは、西暦 100 年 1 月 1 日から 9999 年 12 月 31 日までの日付を処理します。  `COleDateTime` クラスではグレゴリオ暦が使用され、ユリウス暦はサポートされません。  `COleDateTime` は夏時間を無視します。  詳細については、「[日付と時刻 : オートメーションのサポート](../Topic/Date%20and%20Time:%20Automation%20Support.md)」を参照してください。  
  
> [!NOTE]
>  1900 年以降の日付についてのみ、`%y` 書式を使用して 2 桁の年を取得できます。  1900 年より前の日付に `%y` 書式を使用すると、コードで ASSERT エラーが生成されます。  
  
 この型は、日付だけ、または時刻だけの値を表すためにも使用されます。  通常は、日付 0 \(1899 年 12 月 30 日\) は時刻だけの値として使用され、時刻 00:00 \(深夜\) は日付だけの値として使用されます。  
  
 100 未満の日付を使用して `COleDateTime` オブジェクトを作成した場合、その日付は受け付けられますが、以降の `GetYear`、`GetMonth`、`GetDay`、`GetHour`、`GetMinute`、および `GetSecond` の呼び出しは失敗し、\-1 が返されます。  以前は、2 桁の日付を使用できましたが、MFC 4.2 以降では 100 以上の日付を使用する必要があります。  
  
 この問題を回避するには、4 桁の年数を指定します。  次に例を示します。  
  
 [!code-cpp[NVC_ATLMFC_Utilities#1](../../atl-mfc-shared/codesnippet/CPP/coledatetime-class_1.cpp)]  
  
 `COleDateTime` 値の基本的な算術演算には、コンパニオン クラスである [COleDateTimeSpan](../Topic/COleDateTimeSpan%20Class.md) が使用されます。  `COleDateTimeSpan` 値は時間間隔を定義します。  これらのクラス間の関係は、[CTime クラス](../Topic/CTime%20Class.md)と [CTimeSpan クラス](../../atl-mfc-shared/reference/ctimespan-class.md)の関係に似ています。  
  
 `COleDateTime` クラスおよび `COleDateTimeSpan` クラスの詳細については、「[日付と時刻 : オートメーションのサポート](../Topic/Date%20and%20Time:%20Automation%20Support.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** のヘッダーATLComTime.h  
  
## 参照  
 [COleVariant クラス](../../mfc/reference/colevariant-class.md)   
 [CTime クラス](../Topic/CTime%20Class.md)   
 [CTimeSpan クラス](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC の共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)