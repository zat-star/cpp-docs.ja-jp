---
title: "加算クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CFileTime
- CFileTime
- ATL.CFileTime
dev_langs:
- C++
helpviewer_keywords:
- CFileTime class
- shared classes, CFileTime
ms.assetid: 1a358a65-1383-4124-b0d4-59b026e6860f
caps.latest.revision: 18
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
ms.openlocfilehash: 5ff7abc32093691d230787e8eb2d859bb4e77428
ms.lasthandoff: 02/24/2017

---
# <a name="cfiletime-class"></a>加算クラス
このクラスは、ファイルに関連付けられた日付と時刻の値を管理するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CFileTime :  public FILETIME
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFileTime::CFileTime](#cfiletime)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFileTime::GetCurrentTime](#getcurrenttime)|この静的関数を取得する、`CFileTime`を現在のシステム日付と時刻を表すオブジェクト。|  
|[CFileTime::GetTime](#gettime)|時刻を取得するには、このメソッドを呼び出して、`CFileTime`オブジェクトです。|  
|[CFileTime::LocalToUTC](#localtoutc)|ローカル ファイルの時刻を世界協定時刻 (UTC) のファイル時刻に変換するには、このメソッドを呼び出します。|  
|[CFileTime::SetTime](#settime)|によって格納された日時を設定するには、このメソッドを呼び出して、`CFileTime`オブジェクトです。|  
|[CFileTime::UTCToLocal](#utctolocal)|時刻、世界協定時刻 (UTC) に基づいてファイルをローカル時刻に変換するには、このメソッドを呼び出します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CFileTime::operator-](#operator_-)|この演算子を使用で減算を実行する、`CFileTime`または`CFileTimeSpan`オブジェクトです。|  
|[CFileTime::operator! =](#operator_neq)|2 つを比較して`CFileTime`の非等値オブジェクトです。|  
|[CFileTime::operator +](#operator_add)|この演算子は、`CFileTimeSpan` オブジェクトで加算を実行するために使用します。|  
|[CFileTime::operator + = 演算子](#operator_add_eq)|この演算子は、`CFileTimeSpan` オブジェクトで加算を実行し、結果を現在のオブジェクトに代入するために使用します。|  
|[CFileTime::operator&lt;](#operator_lt)|この演算子は、2 つの `CFileTime` オブジェクトを比較して、小さい方を決定します。|  
|[CFileTime::operator&lt;=](#operator_lt_eq)|この演算子では、2 つの `CFileTime` オブジェクトを比較して、等しいかどうか、または小さい方を決定します。|  
|[CFileTime::operator =](#operator_eq)|代入演算子です。|  
|[CFileTime::operator =](#operator_-_eq)|この演算子を使用で減算を実行する、`CFileTimeSpan`オブジェクトし、結果を現在のオブジェクトに代入します。|  
|[CFileTime::operator = =](#operator_eq_eq)|この演算子は、2 つの `CFileTime` オブジェクトが等しいかどうかを比較します。|  
|[CFileTime::operator&gt;](#operator_gt)|この演算子は、2 つの `CFileTime` オブジェクトを比較して、大きい方を決定します。|  
|[CFileTime::operator&gt;=](#operator_gt_eq)|この演算子は、2 つの `CFileTime` オブジェクトを比較して、等しいかどうか、または大きい方を決定します。|  
  
### <a name="public-constants"></a>パブリック定数  
  
|名前|説明|  
|----------|-----------------|  
|[CFileTime::Day](#day)|1 日を構成するための静的データ メンバーが 100 ナノ秒間隔の数を格納します。|  
|[CFileTime::Hour](#hour)|1 時間を構成するための静的データ メンバーが 100 ナノ秒間隔の数を格納します。|  
|[CFileTime::Millisecond](#millisecond)|1 ミリ秒を 100 ナノ秒間隔の数が格納される静的データ メンバーを構成します。|  
|[CFileTime::Minute](#minute)|1 分を構成するための 100 ナノ秒間隔の数が格納される静的データ メンバーです。|  
|[CFileTime::Second](#second)|1 秒間を構成するための静的データ メンバーが 100 ナノ秒間隔の数を格納します。|  
|[CFileTime::Week](#week)|1 週間を構成するための 100 ナノ秒間隔の数が格納される静的データ メンバーです。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、作成、アクセスおよびファイルの変更に関連付けられた日付と時刻の値を管理するためのメソッドを提供します。 メソッドとこのクラスのデータでよく使用されますと共に`CFileTimeSpan`相対時間値の処理のオブジェクト。  
  
 日付と時刻の値は、1601 年 1 月 1 日から 100 ナノ秒間隔の数を表す 64 ビット値として格納されます。 これは、世界協定時刻 (UTC) 形式です。  
  
 計算を簡単には、次の静的な const メンバー変数が用意されています。  
  
|メンバー変数|100 ナノ秒間隔の数|  
|---------------------|-----------------------------------------|  
|Millisecond|10,000|  
|Second|ミリ秒 * 1,000|  
|Minute|2 番目 * 60|  
|Hour|分 * 60|  
|Day|時間 * 24|  
|週|1 日 * 7|  
  
 **注**すべてのファイル システムの作成を記録でき、最終アクセス時刻およびすべてのファイル システム、同じ方法でそれらを記録します。 Windows NT FAT ファイル システム上の例を作成するためのある時間の解像度は 10 ミリ秒、書き込み時間は 2 秒の解像度およびアクセス時間が 1 日 (アクセス日) の解像度です。 NTFS では、アクセス時間は 1 時間の解像度を持ちます。 さらに、FAT は現地時間でディスク上の時刻を記録しますが、NTFS がディスク上の時刻を UTC に記録します。 詳細については、次を参照してください。[ファイル時間](http://msdn.microsoft.com/library/windows/desktop/ms724290)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `FILETIME`  
  
 `CFileTime`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atltime.h  
  
##  <a name="a-namecfiletimea--cfiletimecfiletime"></a><a name="cfiletime"></a>CFileTime::CFileTime  
 コンストラクターです。  
  
```
CFileTime() throw();
CFileTime(const FILETIME& ft) throw();
CFileTime(ULONGLONG nTime) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `ft`  
 A [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)構造体。  
  
 `nTime`  
 日付と時刻を 64 ビット値として表されます。  
  
### <a name="remarks"></a>コメント  
 `CFileTime`を既存の日付と時刻からを使用してオブジェクトを作成できる、`FILETIME`構造体、または 64 ビット値 (ローカルまたは時刻を世界協定時刻 (UTC)) として表されます。 既定のコンス トラクターは、時間を 0 に設定します。  
  
##  <a name="a-namedaya--cfiletimeday"></a><a name="day"></a>CFileTime::Day  
 1 日を構成するための静的データ メンバーが 100 ナノ秒間隔の数を格納します。  
  
```
static const ULONGLONG Day = Hour* 24;
```  
  
### <a name="example"></a>例  
 例を参照してください[CFileTime::Millisecond](#millisecond)します。  
  
##  <a name="a-namegetcurrenttimea--cfiletimegetcurrenttime"></a><a name="getcurrenttime"></a>CFileTime::GetCurrentTime  
 この静的関数を取得する、`CFileTime`を現在のシステム日付と時刻を表すオブジェクト。  
  
```
static CFileTime GetCurrentTime() throw();
```  
  
### <a name="return-value"></a>戻り値  
 現在のシステム日付と時刻を世界協定時刻 (UTC) 形式で返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles #&41;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_1.cpp)]  
  
##  <a name="a-namegettimea--cfiletimegettime"></a><a name="gettime"></a>CFileTime::GetTime  
 時刻を取得するには、このメソッドを呼び出して、`CFileTime`オブジェクトです。  
  
```
ULONGLONG GetTime() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 日付と時刻をローカルまたは世界協定時刻 (UTC) 形式のいずれかである可能性があります、64 ビットの数値として返します。  
  
##  <a name="a-namehoura--cfiletimehour"></a><a name="hour"></a>CFileTime::Hour  
 1 時間を構成するための静的データ メンバーが 100 ナノ秒間隔の数を格納します。  
  
```
static const ULONGLONG Hour = Minute* 60;
```  
  
### <a name="example"></a>例  
 例を参照してください[CFileTime::Millisecond](#millisecond)します。  
  
##  <a name="a-namelocaltoutca--cfiletimelocaltoutc"></a><a name="localtoutc"></a>CFileTime::LocalToUTC  
 ローカル ファイルの時刻を世界協定時刻 (UTC) のファイル時刻に変換するには、このメソッドを呼び出します。  
  
```
CFileTime LocalToUTC() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します。、 `CFileTime` UTC 形式の時刻を表すオブジェクト。  
  
### <a name="example"></a>例  
 例を参照してください[CFileTime::UTCToLocal](#utctolocal)します。  
  
##  <a name="a-namemilliseconda--cfiletimemillisecond"></a><a name="millisecond"></a>CFileTime::Millisecond  
 1 ミリ秒を 100 ナノ秒間隔の数が格納される静的データ メンバーを構成します。  
  
```
static const ULONGLONG Millisecond = 10000;
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles #&44;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_2.cpp)]  
  
##  <a name="a-nameminutea--cfiletimeminute"></a><a name="minute"></a>CFileTime::Minute  
 1 分を構成するための 100 ナノ秒間隔の数が格納される静的データ メンバーです。  
  
```
static const ULONGLONG Minute = Second* 60;
```  
  
### <a name="example"></a>例  
 例を参照してください[CFileTime::Millisecond](#millisecond)します。  
  
##  <a name="a-nameoperator-a--cfiletimeoperator--"></a><a name="operator_-"></a>CFileTime::operator-  
 この演算子を使用で減算を実行する、`CFileTime`または`CFileTimeSpan`オブジェクトです。  
  
```
CFileTime operator-(CFileTimeSpan span) const throw();
CFileTimeSpan operator-(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 `CFileTimeSpan` オブジェクト。  
  
 `ft`  
 `CFileTime` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します。、`CFileTime`オブジェクトまたは`CFileTimeSpan`2 つのオブジェクト間の時間差の結果を表すオブジェクト。  
  
##  <a name="a-nameoperatorneqa--cfiletimeoperator-"></a><a name="operator_neq"></a>CFileTime::operator! =  
 2 つを比較して`CFileTime`の非等値オブジェクトです。  
  
```
bool operator!=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `ft`  
 比較される `CFileTime` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**比較対象のアイテムがと等しくない場合、`CFileTime`オブジェクト、それ以外の場合**false**します。  
  
##  <a name="a-nameoperatoradda--cfiletimeoperator-"></a><a name="operator_add"></a>CFileTime::operator +  
 この演算子は、`CFileTimeSpan` オブジェクトで加算を実行するために使用します。  
  
```
CFileTime operator+(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します。、`CFileTime`元の時刻との相対的な時間の結果を表すオブジェクト。  
  
##  <a name="a-nameoperatoraddeqa--cfiletimeoperator-"></a><a name="operator_add_eq"></a>CFileTime::operator + = 演算子  
 この演算子は、`CFileTimeSpan` オブジェクトで加算を実行し、結果を現在のオブジェクトに代入するために使用します。  
  
```
CFileTime& operator+=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 取得、更新された`CFileTime`元の時刻との相対的な時間の結果を表すオブジェクト。  
  
##  <a name="a-nameoperatorlta--cfiletimeoperator-lt"></a><a name="operator_lt"></a>CFileTime::operator&lt;  
 この演算子は、2 つの `CFileTime` オブジェクトを比較して、小さい方を決定します。  
  
```
bool operator<(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `ft`  
 比較される `CFileTime` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**最初のオブジェクトが、1 秒より小さい (前の時刻) の場合**false**それ以外の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles #&43;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_3.cpp)]  
  
##  <a name="a-nameoperatorlteqa--cfiletimeoperator-lt"></a><a name="operator_lt_eq"></a>CFileTime::operator&lt;=  
 この演算子では、2 つの `CFileTime` オブジェクトを比較して、等しいかどうか、または小さい方を決定します。  
  
```
bool operator<=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `ft`  
 比較される `CFileTime` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**最初のオブジェクト (前の時刻) よりも小さいか等しい場合、2 番目にそれ以外の場合**false**します。  
  
##  <a name="a-nameoperatoreqa--cfiletimeoperator-"></a><a name="operator_eq"></a>CFileTime::operator =  
 代入演算子です。  
  
```
CFileTime& operator=(const FILETIME& ft) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `ft`  
 A`CFileTime`新しい時刻と日付を含むオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 取得、更新された`CFileTime`オブジェクトです。  
  
##  <a name="a-nameoperator-eqa--cfiletimeoperator--"></a><a name="operator_-_eq"></a>CFileTime::operator =  
 この演算子を使用で減算を実行する、`CFileTimeSpan`オブジェクトし、結果を現在のオブジェクトに代入します。  
  
```
CFileTime& operator-=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 A`CFileTimeSpan`減算する相対的な時間を表すオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 取得、更新された`CFileTime`オブジェクトです。  
  
##  <a name="a-nameoperatoreqeqa--cfiletimeoperator-"></a><a name="operator_eq_eq"></a>CFileTime::operator = =  
 この演算子は、2 つの `CFileTime` オブジェクトが等しいかどうかを比較します。  
  
```
bool operator==(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `ft`  
 `CFileTime`と比較するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true** 、オブジェクトが等しい場合、それ以外の場合**false**します。  
  
##  <a name="a-nameoperatorgta--cfiletimeoperator-gt"></a><a name="operator_gt"></a>CFileTime::operator&gt;  
 この演算子は、2 つの `CFileTime` オブジェクトを比較して、大きい方を決定します。  
  
```
bool operator>(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `ft`  
 比較される `CFileTime` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true** (後の時刻) の最初のオブジェクトがより大きい場合は、2 番目よりもそれ以外の場合**false**します。  
  
##  <a name="a-nameoperatorgteqa--cfiletimeoperator-gt"></a><a name="operator_gt_eq"></a>CFileTime::operator&gt;=  
 この演算子は、2 つの `CFileTime` オブジェクトを比較して、等しいかどうか、または大きい方を決定します。  
  
```
bool operator>=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `ft`  
 比較される `CFileTime` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**最初のオブジェクト (後の時刻) より大きいか等しい場合、2 番目にそれ以外の場合**false**します。  
  
##  <a name="a-nameseconda--cfiletimesecond"></a><a name="second"></a>CFileTime::Second  
 1 日を構成するための静的データ メンバーが 100 ナノ秒間隔の数を格納します。  
  
```
static const ULONGLONG Second = Millisecond* 1000;
```  
  
### <a name="example"></a>例  
 例を参照してください[CFileTime::Millisecond](#millisecond)します。  
  
##  <a name="a-namesettimea--cfiletimesettime"></a><a name="settime"></a>CFileTime::SetTime  
 によって格納された日時を設定するには、このメソッドを呼び出して、`CFileTime`オブジェクトです。  
  
```
void SetTime(ULONGLONG nTime) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nTime`  
 日付と時刻をローカル アカウントまたは世界協定時刻 (UTC) 形式で表す 64 ビット値。  
  
##  <a name="a-nameutctolocala--cfiletimeutctolocal"></a><a name="utctolocal"></a>CFileTime::UTCToLocal  
 時刻、世界協定時刻 (UTC) に基づいてファイルをローカル時刻に変換するには、このメソッドを呼び出します。  
  
```
CFileTime UTCToLocal() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します。、`CFileTime`ファイルのローカル時刻の形式の時刻を表すオブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles #&42;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_4.cpp)]  
  
##  <a name="a-nameweeka--cfiletimeweek"></a><a name="week"></a>CFileTime::Week  
 1 週間を構成するための 100 ナノ秒間隔の数が格納される静的データ メンバーです。  
  
```
static const ULONGLONG Week = Day* 7;
```  
  
### <a name="example"></a>例  
 例を参照してください[CFileTime::Millisecond](#millisecond)します。  
  
## <a name="see-also"></a>関連項目  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [持つクラス](../../atl-mfc-shared/reference/cfiletimespan-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL と MFC クラスの共有](../../atl-mfc-shared/atl-mfc-shared-classes.md)



