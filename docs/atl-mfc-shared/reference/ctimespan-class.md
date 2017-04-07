---
title: "CTimeSpan クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTimeSpan
- ATLTIME/ATL::CTimeSpan
- ATLTIME/ATL::CTimeSpan::CTimeSpan
- ATLTIME/ATL::CTimeSpan::Format
- ATLTIME/ATL::CTimeSpan::GetDays
- ATLTIME/ATL::CTimeSpan::GetHours
- ATLTIME/ATL::CTimeSpan::GetMinutes
- ATLTIME/ATL::CTimeSpan::GetSeconds
- ATLTIME/ATL::CTimeSpan::GetTimeSpan
- ATLTIME/ATL::CTimeSpan::GetTotalHours
- ATLTIME/ATL::CTimeSpan::GetTotalMinutes
- ATLTIME/ATL::CTimeSpan::GetTotalSeconds
- ATLTIME/ATL::CTimeSpan::Serialize64
dev_langs:
- C++
helpviewer_keywords:
- elapsed time, CTimeSpan object
- timespan
- time span
- CTimeSpan class
- shared classes, CTimeSpan
- time, elapsed
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5c76411f6c1302d406b07cc79d9c544e3ad8c43b
ms.lasthandoff: 02/24/2017

---
# <a name="ctimespan-class"></a>CTimeSpan クラス
時間間隔の秒数として内部的に格納されている、時間です。  
  
## <a name="syntax"></a>構文  
  
```
class CTimeSpan
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CTimeSpan::CTimeSpan](#ctimespan)|構築`CTimeSpan`さまざまな方法でオブジェクトです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTimeSpan::Format](#format)|変換、`CTimeSpan`書式設定された文字列にします。|  
|[CTimeSpan::GetDays](#getdays)|この完全な日数を表す値を返します`CTimeSpan`します。|  
|[CTimeSpan::GetHours](#gethours)|現在の日付 (-23 ~ 23) の時間数を表す値を返します。|  
|[CTimeSpan::GetMinutes](#getminutes)|現在 (-59 ~ 59) で分単位の数を表す値を返します。|  
|[CTimeSpan::GetSeconds](#getseconds)|現在 (-59 ~ 59) の秒数を表す値を返します。|  
|[CTimeSpan::GetTimeSpan](#gettimespan)|値を返す、`CTimeSpan`オブジェクトです。|  
|[CTimeSpan::GetTotalHours](#gettotalhours)|この時間の合計数を表す値を返します`CTimeSpan`します。|  
|[CTimeSpan::GetTotalMinutes](#gettotalminutes)|この分数の合計数を表す値を返します`CTimeSpan`します。|  
|[CTimeSpan::GetTotalSeconds](#gettotalseconds)|この完全な秒数の合計数を表す値を返します`CTimeSpan`します。|  
|[CTimeSpan::Serialize64](#serialize64)|アーカイブからのデータをシリアル化します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子: +](#operator_add_-)|追加し、減算`CTimeSpan`オブジェクトです。|  
|[operator + = – =](#operator_add_eq_-_eq)|追加し、減算、`CTimeSpan`オブジェクトからこのへ`CTimeSpan`します。|  
|[演算子 = =<>](#ctimespan_comparison_operators)|2 つの相対的な時間の値を比較します。|  
  
## <a name="remarks"></a>コメント  
 `CTimeSpan`基本クラスはありません。  
  
 `CTimeSpan`関数は、さまざまな組み合わせで、日、時間、分、秒および秒に変換します。  
  
 `CTimeSpan`でオブジェクトが格納されている、 **_ _time64_t**構造体は、8 バイトです。  
  
 コンパニオン クラス[CTime](../../atl-mfc-shared/reference/ctime-class.md)、絶対時刻を表します。  
  
 `CTime`と`CTimeSpan`用の派生クラスではありません。 両方のサイズの仮想関数が存在しないため`CTime`と`CTimeSpan`オブジェクトは、厳密に 8 バイトです。 ほとんどのメンバー関数はインラインです。  
  
 使用する方法について`CTimeSpan`、記事を参照して[日付と時刻](../../atl-mfc-shared/date-and-time.md)、および[時間管理](../../c-runtime-library/time-management.md)で、*ランタイム ライブラリ リファレンス*します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atltime.h  
  
##  <a name="ctimespan_comparison_operators"></a>CTimeSpan 比較演算子  
 比較演算子です。  
  
```
bool operator==(CTimeSpan span) const throw();
bool operator!=(CTimeSpan span) const throw();
bool operator<(CTimeSpan span) const throw();
bool operator>(CTimeSpan span) const throw();
bool operator<=(CTimeSpan span) const throw();
bool operator>=(CTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
  
 比較対象のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 これらの演算子は、2 つの相対的な時間の値を比較します。 返される**true**条件が true、それ以外の場合**false**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&169;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]  
  
##  <a name="ctimespan"></a>CTimeSpan::CTimeSpan  
 構築`CTimeSpan`さまざまな方法でオブジェクトです。  
  
```
CTimeSpan() throw();
CTimeSpan(__time64_t time) throw();

CTimeSpan(  
 LONG lDays,
 int nHours,
 int nMins,
 int nSecs) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *timeSpanSrc*  
 A`CTimeSpan`は既に存在するオブジェクト。  
  
 `time`  
 A **_ _time64_t**時間間隔の秒数は、時刻の値。 Visual C version 6.0 およびそれ以前、`time`の値が`time_t`です。 Visual C .NET か、または後で自動的に変換する`time_t`パラメーターを**_ _time64_t**します。  
  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 日、時、分、および秒にそれぞれします。  
  
### <a name="remarks"></a>コメント  
 これらすべてのコンス トラクターを作成、新しい`CTimeSpan`オブジェクトが指定された相対時間を使用して初期化します。 各コンス トラクターは、次に示します。  
  
- **CTimeSpan ();**初期化されていない構築`CTimeSpan`オブジェクトです。  
  
- **CTimeSpan (const CTimeSpan >/documents/report1.rdl」の);**を構築、`CTimeSpan`オブジェクトから`CTimeSpan`値。  
  
- **CTimeSpan (_ _time64_t) です。**を構築、`CTimeSpan`オブジェクトから、 **_ _time64_t**型です。  
  
- **CTimeSpan (長い**、 **int、int、int);**構築、`CTimeSpan`の各構成要素からオブジェクトが、次の範囲に制限します。  
  
    |コンポーネント|範囲|  
    |---------------|-----------|  
    |`lDays`|0 –&25;,000 (概算)|  
    |`nHours`|0–23|  
    |`nMins`|0–59|  
    |`nSecs`|0–59|  
  
 Microsoft Foundation Class ライブラリのデバッグ バージョンでは、1 つまたは複数の時刻コンポーネントが範囲外アサートすることに注意してください。 ユーザーの責任において、呼び出しの前に引数を検証することをお勧めします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&162;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]  
  
##  <a name="format"></a>CTimeSpan::Format  
 これに対応する書式設定された文字列を生成`CTimeSpan`します。  
  
```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `pFormat`, `pszFormat`  
 書式文字列のような`printf`文字列の書式を設定します。 割合に続くコードの書式設定 ( `%`) 署名、削除され、対応する、`CTimeSpan`コンポーネントです。 書式指定文字列内の文字は、返される文字列に変更されていないコピーされます。 値と書式設定コードの意味**形式**以下に示します。  
  
- **%D**この日数の合計`CTimeSpan`  
  
- **%H**現在の日の時間  
  
- **%M**現在の時間の分数  
  
- **%S**現在の時間 (秒)  
  
- **%%**パーセント記号  
  
 `nID`  
 この形式を識別する文字列の ID です。  
  
### <a name="return-value"></a>戻り値  
 A`CString`書式設定された時刻を含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 ライブラリのデバッグ バージョンでは、書式設定コードをチェックし、コードが上記の一覧でないかどうかはアサートします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&163;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]  
  
##  <a name="getdays"></a>CTimeSpan::GetDays  
 この完全な日数を表す値を返します`CTimeSpan`します。  
  
```
LONGLONG GetDays() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 時間間隔で 24 時間日単位の数を返します。 この値は、時間が負の場合は、負である可能性があります。  
  
### <a name="remarks"></a>コメント  
 夏時間の原因となる注`GetDays`可能性のある予想外の結果を返すようにします。 たとえばと夏時間が有効で**GetDays**年 4 月 1 日が 1 時間に短縮し、そのため、完了日とは見なされませんので、29、30 でとして 4 月 1 日から 5 月 1日までの日数の数を報告します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&164;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]  
  
##  <a name="gethours"></a>CTimeSpan::GetHours  
 現在の日付 (-23 ~ 23) の時間数を表す値を返します。  
  
```
LONG GetHours() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 現在の日付の時間数を返します。 範囲は、-23 ~ 23 です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&165;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]  
  
##  <a name="getminutes"></a>CTimeSpan::GetMinutes  
 現在 (-59 ~ 59) で分単位の数を表す値を返します。  
  
```
LONG GetMinutes() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 現在の時間の分数を返します。 範囲は、-59 59 からです。  
  
### <a name="example"></a>例  
 例を参照してください[GetHours](#gethours)します。  
  
##  <a name="getseconds"></a>CTimeSpan::GetSeconds  
 現在 (-59 ~ 59) の秒数を表す値を返します。  
  
```
LONG GetSeconds() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 現在の分の秒数を返します。 範囲は、-59 59 からです。  
  
### <a name="example"></a>例  
 例を参照してください[GetHours](#gethours)します。  
  
##  <a name="gettimespan"></a>CTimeSpan::GetTimeSpan  
 値を返す、`CTimeSpan`オブジェクトです。  
  
```
__ time64_t GetTimeSpan() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 現在の値を返して、`CTimeSpan`オブジェクトです。  
  
##  <a name="gettotalhours"></a>CTimeSpan::GetTotalHours  
 この時間の合計数を表す値を返します`CTimeSpan`します。  
  
```
LONGLONG GetTotalHours() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この時間の合計数を返す`CTimeSpan`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&166;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]  
  
##  <a name="gettotalminutes"></a>CTimeSpan::GetTotalMinutes  
 この分数の合計数を表す値を返します`CTimeSpan`します。  
  
```
LONGLONG GetTotalMinutes() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この分数の合計数を返す`CTimeSpan`します。  
  
### <a name="example"></a>例  
 例を参照してください[従来](#gettotalhours)します。  
  
##  <a name="gettotalseconds"></a>CTimeSpan::GetTotalSeconds  
 この完全な秒数の合計数を表す値を返します`CTimeSpan`します。  
  
```
LONGLONG GetTotalSeconds() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この完全な秒数の合計を返す`CTimeSpan`します。  
  
### <a name="example"></a>例  
 例を参照してください[従来](#gettotalhours)します。  
  
##  <a name="operator_add_-"></a>CTimeSpan::operator +、-  
 追加し、減算`CTimeSpan`オブジェクトです。  
  
```
CTimeSpan operator+(CTimeSpan span) const throw();
CTimeSpan operator-(CTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 追加する値、`CTimeSpan`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 A`CTimeSpan`操作の結果を表すオブジェクト。  
  
### <a name="remarks"></a>コメント  
 これら&2; つの演算子を使用する加算および減算できます`CTimeSpan`と個々 のオブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&167;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>CTimeSpan::operator + =、=  
 追加し、減算、`CTimeSpan`オブジェクトからこのへ`CTimeSpan`します。  
  
```
CTimeSpan& operator+=(CTimeSpan span) throw();
CTimeSpan& operator-=(CTimeSpan span) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 追加する値、`CTimeSpan`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 更新された`CTimeSpan`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 これらの演算子では、追加または削除することができる、`CTimeSpan`オブジェクトからこのへ`CTimeSpan`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&168;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]  
  
##  <a name="serialize64"></a>CTimeSpan::Serialize64  
  
> [!NOTE]
>  このメソッドを MFC プロジェクトで使用できるだけです。  
  
 アーカイブとの間のメンバー変数に関連付けられているデータをシリアル化します。  
  
```
CArchive& Serialize64(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 `ar`  
 `CArchive`を更新するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 更新された`CArchive`オブジェクトです。  
  
## <a name="see-also"></a>関連項目  
 [asctime、_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [_ftime、_ftime32、_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime、_localtime32、_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [strftime、wcsftime、_strftime_l、_wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL と MFC クラスの共有](../../atl-mfc-shared/atl-mfc-shared-classes.md)



