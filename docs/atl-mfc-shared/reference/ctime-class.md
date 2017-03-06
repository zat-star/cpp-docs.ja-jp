---
title: "CTime クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CTime
- CTime
- ATL::CTime
dev_langs:
- C++
helpviewer_keywords:
- CTime class
- shared classes, CTime
ms.assetid: 0a299544-485b-48dc-9d3c-fdc30f57d612
caps.latest.revision: 30
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
ms.sourcegitcommit: 1a00023e4d3e31ddb6381e90a50231449b1de18d
ms.openlocfilehash: 56b8b5c3574a7a53a4e259412b1b1326973bcac9
ms.lasthandoff: 02/28/2017

---
# <a name="ctime-class"></a>CTime クラス
絶対時刻と日付を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CTime  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CTime::CTime](#ctime)|構築`CTime`さまざまな方法でオブジェクトです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTime::Format](#format)|変換、`CTime`オブジェクトを書式設定された文字列に、ローカル タイム ゾーンに基づきます。|  
|[CTime::FormatGmt](#formatgmt)|変換、`CTime`に書式設定された文字列オブジェクト — UTC に基づきます。|  
|[CTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|格納されている時間の情報に変換、 `CTime` Win32 と互換性のある DBTIMESTAMP 構造体へのオブジェクト。|  
|[CTime::GetAsSystemTime](#getassystemtime)|格納されている時間の情報に変換、`CTime`を Win32 互換性のあるオブジェクト[SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)構造体。|  
|[CTime::GetCurrentTime](#getcurrenttime)|作成、`CTime`を現在の時刻 (静的メンバー関数) を表すオブジェクト。|  
|[CTime::GetDay](#getday)|によって表される日を返す、`CTime`オブジェクトです。|  
|[CTime::GetDayOfWeek](#getdayofweek)|によって表される曜日を返す、`CTime`オブジェクトです。|  
|[CTime::GetGmtTm](#getgmttm)|分割、`CTime`オブジェクトをコンポーネントに、UTC に基づきます。|  
|[CTime::GetHour](#gethour)|表す時要素を返す、`CTime`オブジェクトです。|  
|[CTime::GetLocalTm](#getlocaltm)|分割、`CTime`オブジェクトをコンポーネントに、ローカル タイム ゾーンに基づきます。|  
|[CTime::GetMinute](#getminute)|によって表される分が返されます、`CTime`オブジェクトです。|  
|[渡して](#getmonth)|表される月を返す、`CTime`オブジェクトです。|  
|[CTime::GetSecond](#getsecond)|によって表される&2; 番目、`CTime`オブジェクトです。|  
|[CTime::GetTime](#gettime)|返します。、 **_ _time64_t**値を、指定された`CTime`オブジェクトです。|  
|[CTime::GetYear](#getyear)|によって表される年を返し、`CTime`オブジェクトです。|  
|[CTime::Serialize64](#serialize64)|アーカイブからのデータをシリアル化します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子: +](#operator_add_-)|これらの演算子は加算し、減算`CTimeSpan`と`CTime`のオブジェクト。|  
|[演算子 + =、=](#operator_add_eq_-_eq)|これらの演算子は加算し、減算、`CTimeSpan`オブジェクトとの間この`CTime`オブジェクトです。|  
|[演算子 =](#operator_eq)|代入演算子です。|  
|[演算子 = =、< ,="">](#ctime_comparison_operators)|比較演算子です。|  
  
## <a name="remarks"></a>コメント  
 `CTime`基本クラスはありません。  
  
 `CTime`値は、世界協定時刻 (グリニッジ標準時、GMT) には、世界協定時刻 (UTC) に基づいています。 参照してください[時間管理](../../c-runtime-library/time-management.md)タイム ゾーンを決定する方法についてです。  
  
 作成するときに、`CTime`オブジェクト、設定、`nDST`を 0 に、その標準時を示すパラメーターは、実際には、0 より大きな値をその夏時間が有効で、または C ランタイム ライブラリ コードの計算に 0 より小さい値にかどうか標準時間と夏時間のどちらが有効にします。 `tm_isdst` は必須フィールドです。 かどうかは設定されていない、その値は未定義とからの戻り値[mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)は予測できません。 場合`timeptr`を以前の呼び出しによって返される、tm 構造体を指す[asctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)、 [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)、または[localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)、`tm_isdst`フィールドには、正しい値が含まれています。  
  
 コンパニオン クラス[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)、時間間隔を表します。  
  
 `CTime`と`CTimeSpan`用の派生クラスではありません。 サイズの仮想関数が存在しないため`CTime`と`CTimeSpan`オブジェクトは、厳密に 8 バイトです。 ほとんどのメンバー関数はインラインです。  
  
> [!NOTE]
>  日付の上限は、12/31/3000 です。 下限は 1970 年 1 月 1 日 12時 00分: 00 AM GMT です。  
  
 使用の詳細については`CTime`、記事を参照して[日付と時刻](../../atl-mfc-shared/date-and-time.md)、および[時間管理](../../c-runtime-library/time-management.md)ランタイム ライブラリ リファレンスです。  
  
> [!NOTE]
>  `CTime` MFC 7.1 から MFC 8.0 に構造を変更します。 シリアル化する場合、`CTime`構造体を使用して、 `operator <<` MFC 8.0 またはそれ以降のバージョンでは、生成されたファイルは解読できません MFC の以前のバージョン。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atltime.h  
  
##  <a name="a-namectimecomparisonoperatorsa--ctime-comparison-operators"></a><a name="ctime_comparison_operators"></a>CTime 比較演算子  
 比較演算子です。  
  
```  
bool operator==(CTime time) const throw(); 
bool operator!=(CTime time) const throw();
bool operator<(CTime time) const throw();
bool operator>(CTime time) const throw();
bool operator<=(CTime time) const throw();
bool operator>=(CTime time) const throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `time`  
 比較される `CTime` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 これらの演算子は&2; つの絶対時刻を比較し、 **true**条件が true、それ以外の場合**false**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&161;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]  
  
##  <a name="a-namectimea--ctimectime"></a><a name="ctime"></a>CTime::CTime  
 新たに作成`CTime`オブジェクトの指定した時刻に初期化します。  
  
```  
CTime() throw(); 
CTime(__time64_t time) throw();
CTime(int nYear, int nMonth, int nDay,
      int nHour, int nMin, int nSec, int nDST = -1);
CTime(WORD wDosDate, WORD wDosTime, int nDST = -1);
CTime(const SYSTEMTIME& st, int nDST = - 1) throw();
CTime(const FILETIME& ft, int nDST = - 1);
CTime(const DBTIMESTAMP& dbts,int nDST = -1) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `timeSrc`  
 示す、`CTime`は既に存在するオブジェクト。  
  
 `time`  
 A **_ _time64_t**時刻の値は、1970 年 1 月 1 日 UTC (秒数) の数です。 これがローカル時刻に調整されることに注意してください。 たとえば、ニューヨークにして作成した場合、 `CTime` 0、パラメーターを渡すことによって[渡して](#getmonth)は 12 を返します。  
  
 Visual C version 6.0 およびそれ以前、`time`の値が`time_t`です。 Visual C .NET およびそれ以降の変換、`time_t`パラメーターを**_ _time64_t**します。  
  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 新しいにコピーされる日付と時刻の値を示す`CTime`オブジェクトです。  
  
 `nDST`  
 夏時間が有効になっているかどうかを示します。 3 つの値のいずれかを設定できます。  
  
- `nDST`0Standard 時間に設定が有効で。  
  
- `nDST`時刻が有効になって 0Daylight より大きい値に設定します。  
  
- `nDST`既定の 0The よりも小さい値に設定します。 標準時間と夏時間のどちらが有効ではあるかどうかを自動的に計算します。  
  
 `wDosDate`, `wDosTime`  
 MS-DOS 日付と時刻の値は、日付/時刻値に変換され、新しい`CTime`オブジェクトです。  
  
 `st`  
 A [SYSTEMTIME](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/d6609fff-1931-4818-8a26-f042630af0b0/locales/en-us)日付/時刻値に変換され、新しいコピーを構造`CTime`オブジェクトです。  
  
 `ft`  
 A [FILETIME](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/979ce746-dc17-4147-89f8-41d05c5fcc5f/locales/en-us)日付/時刻値に変換され、新しいコピーを構造`CTime`オブジェクトです。  
  
 dbts  
 現在の現地時刻を含む DBTIMESTAMP 構造体への参照。  
  
### <a name="remarks"></a>コメント  
 各コンス トラクターは、次に示します。  
  
- **CTime() です。**初期化されていない構築`CTime`オブジェクトです。 このコンス トラクターを定義できます。`CTime`オブジェクトの配列。 使用する前に有効な値では、そのような配列を初期化する必要があります。  
  
- **CTime (const CTime >/documents/report1.rdl」の);**を構築、`CTime`オブジェクトから`CTime`値。  
  
- **CTime (_ _time64_t) です。**を構築、`CTime`オブジェクトから、 **_ _time64_t**型です。 このコンス トラクターは、UTC 時刻を想定し、結果を保存する前に結果をローカル時刻に変換します。  
  
- **CTime (int、int、)。**を構築、`CTime`現地時間の各コンポーネントの要素からオブジェクトが、次の範囲に制限します。  
  
    |コンポーネント|範囲|  
    |---------------|-----------|  
    |`nYear`|1970–3000|  
    |`nMonth`|1–12|  
    |`nDay`|1–31|  
    |`nHour`|0-23|  
    |`nMin`|0-59|  
    |`nSec`|0-59|  
  
     このコンス トラクターは、UTC への適切な変換を使用できます。 Microsoft Foundation Class ライブラリのデバッグ バージョン アサートの場合は、1 つまたは複数時コンポーネントの範囲外です。 呼び出しの前に引数を検証する必要があります。 このコンス トラクターでは、ローカル タイムが必要です。  
  
- **CTime (WORD、WORD)**を構築、 `CTime` MS-DOS 日付と時刻の値は、指定したオブジェクト。 このコンス トラクターでは、ローカル タイムが必要です。  
  
- **CTime (const SYSTEMTIME >/documents/report1.rdl」の);**を構築、`CTime`からオブジェクトを`SYSTEMTIME`構造体。 このコンス トラクターでは、ローカル タイムが必要です。  
  
- **CTime (const FILETIME >/documents/report1.rdl」の);**を構築、`CTime`からオブジェクトを`FILETIME`構造体。 多くの場合は使用しません`CTime FILETIME`初期化を直接します。 使用する場合、`CFile`にファイルを操作するオブジェクト`CFile::GetStatus`経由のファイルのタイムスタンプを取得、`CTime`オブジェクトを初期化して、`FILETIME`構造体。 このコンス トラクターは、UTC に基づく時間を想定し、自動的に値を現地時刻に結果を保存する前に変換します。  
  
    > [!NOTE]
    >  コンス トラクターを使用して、 **DBTIMESTAMP**パラメーターは、OLEDB.h が含まれる場合にのみ使用できます。  
  
 詳細については、次を参照してください。、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)と[FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 参照してください、 [MS-DOS 日付と時刻](http://msdn.microsoft.com/library/windows/desktop/ms724503)内のエントリ、[!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&148;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]  
  
##  <a name="a-nameformata--ctimeformat"></a><a name="format"></a>CTime::Format  
 日付/時刻値の書式設定された表現を作成するには、このメンバー関数を呼び出します。  
  
```  
CString Format(LPCTSTR pszFormat) const; 
CString Format(UINT nFormatID) const; 
```  
  
### <a name="parameters"></a>パラメーター  
 `pszFormat`  
 書式文字列のような`printf`文字列の書式を設定します。 割合に続くコードの書式設定 ( `%`) 署名、削除され、対応する、`CTime`コンポーネントです。 書式指定文字列内の文字は、返される文字列に変更されていないコピーされます。 ランタイム関数を参照してください[strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)書式指定コードの一覧にします。  
  
 `nFormatID`  
 この形式を識別する文字列の ID です。  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)書式化された時刻を格納しています。  
  
### <a name="remarks"></a>コメント  
 場合はこの状態`CTime`オブジェクトが null、戻り値は空の文字列です。  
  
 このメソッドは、1970 年 1 月 1 日から 3000 年 12 月 31 日、午前 0 時から書式設定する日付時刻値が範囲外の場合に例外をスロー世界協定時刻 (UTC)。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&149;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]  
  
##  <a name="a-nameformatgmta--ctimeformatgmt"></a><a name="formatgmt"></a>CTime::FormatGmt  
 これに対応する書式設定された文字列を生成`CTime`オブジェクトです。  
  
```  
CString FormatGmt(LPCTSTR pszFormat) const; 
CString FormatGmt(UINT nFormatID) const; 
```  
  
### <a name="parameters"></a>パラメーター  
 `pszFormat`  
 ような書式指定文字列の指定、`printf`文字列の書式を設定します。 ランタイム関数を参照してください[strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)詳細です。  
  
 `nFormatID`  
 この形式を識別する文字列の ID です。  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)書式化された時刻を格納しています。  
  
### <a name="remarks"></a>コメント  
 時刻の値は変換されませんし、(utc) に基づいて生成されます。  
  
 このメソッドは、1970 年 1 月 1 日から 3000 年 12 月 31 日、午前 0 時から書式設定する日付時刻値が範囲外の場合に例外をスロー世界協定時刻 (UTC)。  
  
### <a name="example"></a>例  
 例を参照してください[CTime::Format](#format)します。  
  
##  <a name="a-namegetasdbtimestampa--ctimegetasdbtimestamp"></a><a name="getasdbtimestamp"></a>CTime::GetAsDBTIMESTAMP  
 格納されている時刻情報に変換するには、このメンバー関数を呼び出す、 `CTime` Win32 と互換性のある DBTIMESTAMP 構造体へのオブジェクト。  
  
```  
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dbts`  
 現在の現地時刻を含む DBTIMESTAMP 構造体への参照。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 結果として得られる時刻を、参照されている `dbts` 構造体に格納します。 **DBTIMESTAMP**この関数によって初期化データ構造が含まれ、**分数**メンバーがゼロに設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&150;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]  
  
##  <a name="a-namegetassystemtimea--ctimegetassystemtime"></a><a name="getassystemtime"></a>CTime::GetAsSystemTime  
 格納されている時刻情報に変換するには、このメンバー関数を呼び出す、`CTime`を Win32: 互換性のあるオブジェクト[SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)構造体。  
  
```  
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *timeDest*  
 参照、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)の変換後の日付/時刻値を保持する構造体、`CTime`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は true。それ以外の場合は false。  
  
### <a name="remarks"></a>コメント  
 `GetAsSystemTime`参照先の結果として得られる時間を格納*timeDest*構造体。 `SYSTEMTIME`この関数によって初期化データ構造が含まれ、 **wMilliseconds**メンバーがゼロに設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[最適な NVC_ATLMFC_Utilities](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]  
  
##  <a name="a-namegetcurrenttimea--ctimegetcurrenttime"></a><a name="getcurrenttime"></a>CTime::GetCurrentTime  
 返します。、`CTime`を現在の時刻を表すオブジェクト。  
  
```  
static CTime WINAPI GetCurrentTime() throw();
```  
  
### <a name="remarks"></a>コメント  
 現在のシステム日付と時刻を世界協定時刻 (UTC) で返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&152;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]  
  
##  <a name="a-namegetdaya--ctimegetday"></a><a name="getday"></a>CTime::GetDay  
 によって表される日を返す、`CTime`オブジェクトです。  
  
```  
int GetDay() const throw(); 
```  
  
### <a name="return-value"></a>戻り値  
 1 ~ 31 の範囲内のローカル時刻に基づき、月の日を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は`GetLocalTm`、静的に割り当てられた、内部のバッファーを使用します。 このバッファー内のデータは、他の呼び出しによって上書きされます`CTime`メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&153;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]  
  
##  <a name="a-namegetdayofweeka--ctimegetdayofweek"></a><a name="getdayofweek"></a>CTime::GetDayOfWeek  
 によって表される曜日を返す、`CTime`オブジェクトです。  
  
```  
int GetDayOfWeek() const throw(); 
```  
  
### <a name="return-value"></a>戻り値  
 ローカル時刻に基づいて週の曜日を返します。1 = 日曜日、2 = 月曜日、7 = 土曜日です。  
  
### <a name="remarks"></a>コメント  
 この関数は`GetLocalTm`バッファーの割り当てを使用して、内部静的にします。 このバッファー内のデータは、他の呼び出しによって上書きされます`CTime`メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&154;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]  
  
##  <a name="a-namegetgmttma--ctimegetgmttm"></a><a name="getgmttm"></a>CTime::GetGmtTm  
 取得、**構造体 tm**これに含まれている時間の分解を格納している`CTime`オブジェクトです。  
  
```  
struct tm* GetGmtTm(struct tm* ptm) const; 
```  
  
### <a name="parameters"></a>パラメーター  
 `ptm`  
 時間のデータを受け取るバッファーへのポインター。 このポインターが場合**NULL**例外がスローされます。  
  
### <a name="return-value"></a>戻り値  
 入力でへのポインター**構造体 tm**時にインクルード ファイルで定義されています。H. 参照してください[gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)構造体。  
  
### <a name="remarks"></a>コメント  
 `GetGmtTm`UTC を返します。  
  
 `ptm` として `NULL` を使用することはできません。 これで、以前の動作に戻す場合`ptm`可能性があります`NULL`を静的に割り当てられた、内部のバッファーを使用することを示す、未定義、`_SECURE_ATL`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&155;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]  
  
##  <a name="a-namegethoura--ctimegethour"></a><a name="gethour"></a>CTime::GetHour  
 表す時要素を返す、`CTime`オブジェクトです。  
  
```  
int GetHour() const throw(); 
```  
  
### <a name="return-value"></a>戻り値  
 0 ~ 23 の範囲内のローカル時刻に基づいて時間を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は`GetLocalTm`バッファーの割り当てを使用して、内部静的にします。 このバッファー内のデータは、他の呼び出しによって上書きされます`CTime`メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&156;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]  
  
##  <a name="a-namegetlocaltma--ctimegetlocaltm"></a><a name="getlocaltm"></a>CTime::GetLocalTm  
 取得、**構造体 tm**これに含まれている時間の分解を含む`CTime`オブジェクトです。  
  
```  
struct tm* GetLocalTm(struct tm* ptm) const; 
```  
  
### <a name="parameters"></a>パラメーター  
 `ptm`  
 時間のデータを受け取るバッファーへのポインター。 このポインターが場合**NULL**例外がスローされます。  
  
### <a name="return-value"></a>戻り値  
 入力でへのポインター**構造体 tm**時にインクルード ファイルで定義されています。H. 参照してください[gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)構造体。  
  
### <a name="remarks"></a>コメント  
 `GetLocalTm`ローカル時刻を返します。  
  
 `ptm` として `NULL` を使用することはできません。 これで、以前の動作に戻す場合`ptm`可能性があります`NULL`を静的に割り当てられた、内部のバッファーを使用することを示す、未定義、`_SECURE_ATL`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&157;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]  
  
##  <a name="a-namegetminutea--ctimegetminute"></a><a name="getminute"></a>CTime::GetMinute  
 によって表される分が返されます、`CTime`オブジェクトです。  
  
```  
int GetMinute() const throw(); 
```  
  
### <a name="return-value"></a>戻り値  
 0 ~ 59 の範囲内のローカル時刻に基づいて分を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は`GetLocalTm`バッファーの割り当てを使用して、内部静的にします。 このバッファー内のデータは、他の呼び出しによって上書きされます`CTime`メンバー関数。  
  
### <a name="example"></a>例  
 例を参照してください[GetHour](#gethour)します。  
  
##  <a name="a-namegetmontha--ctimegetmonth"></a><a name="getmonth"></a>渡して  
 表される月を返す、`CTime`オブジェクトです。  
  
```  
int GetMonth() const throw(); 
```  
  
### <a name="return-value"></a>戻り値  
 1 ~ 12 の範囲内のローカル時刻に基づき、月を返します (1 年 1 月 =)。  
  
### <a name="remarks"></a>コメント  
 この関数は`GetLocalTm`バッファーの割り当てを使用して、内部静的にします。 このバッファー内のデータは、他の呼び出しによって上書きされます`CTime`メンバー関数。  
  
### <a name="example"></a>例  
 例を参照してください[GetDay](#getday)します。  
  
##  <a name="a-namegetseconda--ctimegetsecond"></a><a name="getsecond"></a>CTime::GetSecond  
 によって表される&2; 番目、`CTime`オブジェクトです。  
  
```  
int GetSecond() const throw(); 
```  
  
### <a name="return-value"></a>戻り値  
 2 番目、0 ~ 59 の範囲内のローカル時間に基づきます。  
  
### <a name="remarks"></a>コメント  
 この関数は`GetLocalTm`バッファーの割り当てを使用して、内部静的にします。 このバッファー内のデータは、他の呼び出しによって上書きされます`CTime`メンバー関数。  
  
### <a name="example"></a>例  
 例を参照してください[GetHour](#gethour)します。  
  
##  <a name="a-namegettimea--ctimegettime"></a><a name="gettime"></a>CTime::GetTime  
 返します。、 **_ _time64_t**値を、指定された`CTime`オブジェクトです。  
  
```  
__time64_t GetTime() const throw(); 
```  
  
### <a name="return-value"></a>戻り値  
 **GetTime**現在間の秒数を返す`CTime`オブジェクトと 1970 年 1 月 1 日です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&158;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]  
  
##  <a name="a-namegetyeara--ctimegetyear"></a><a name="getyear"></a>CTime::GetYear  
 によって表される年を返し、`CTime`オブジェクトです。  
  
```  
int GetYear();
```  
  
### <a name="return-value"></a>戻り値  
 年 1 月の範囲内のローカル時刻に基づき、年を返す 1,1970、2038 年 1 月 18日 (包含的) にします。  
  
### <a name="remarks"></a>コメント  
 この関数は`GetLocalTm`バッファーの割り当てを使用して、内部静的にします。 このバッファー内のデータは、他の呼び出しによって上書きされます`CTime`メンバー関数。  
  
### <a name="example"></a>例  
 例を参照してください[GetDay](#getday)します。  
  
##  <a name="a-nameoperatoreqa--ctimeoperator-"></a><a name="operator_eq"></a>CTime::operator =  
 代入演算子です。  
  
```  
CTime& operator=(__time64_t time) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `time`  
 新しい日付/時刻値。  
  
### <a name="return-value"></a>戻り値  
 更新された`CTime`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 このオーバー ロード代入演算子は、これに、元の時刻をコピー`CTime`オブジェクトです。 内部時刻ストレージ、`CTime`オブジェクトはタイム ゾーンに依存しません。 タイム ゾーンの変換は、割り当ての際に必要ではありません。  
  
##  <a name="a-nameoperatoradd-a--ctimeoperator---"></a><a name="operator_add_-"></a>CTime::operator +、-  
 これらの演算子は加算し、減算`CTimeSpan`と`CTime`のオブジェクト。  
  
```  
CTime operator+(CTimeSpan timeSpan) const throw(); 
CTime operator-(CTimeSpan timeSpan) const throw(); 
CTimeSpan operator-(CTime time) const throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 *timeSpan*  
 `CTimeSpan`加算または減算するオブジェクト。  
  
 `time`  
 `CTime`減算します。  
  
### <a name="return-value"></a>戻り値  
 A`CTime`または`CTimeSpan`操作の結果を表すオブジェクト。  
  
### <a name="remarks"></a>コメント  
 `CTime`オブジェクトは、絶対時刻を表す`CTimeSpan`オブジェクトは相対的な時間を表します。 最初の&2; つの演算子を使用すると、加算し、減算`CTimeSpan`オブジェクトとの間`CTime`オブジェクトです。 3 番目の演算子では、1 を減算することができます`CTime`を譲渡して別のオブジェクト、`CTimeSpan`オブジェクトです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&159;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]  
  
##  <a name="a-nameoperatoraddeq-eqa--ctimeoperator---"></a><a name="operator_add_eq_-_eq"></a>CTime::operator + =、=  
 これらの演算子は加算し、減算、`CTimeSpan`オブジェクトとの間この`CTime`オブジェクトです。  
  
```  
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 `CTimeSpan`加算または減算するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 更新された`CTime`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 これらの演算子では、追加または削除することができる、`CTimeSpan`にオブジェクトがこれから`CTime`オブジェクトです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&160;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]  
  
##  <a name="a-nameserialize64a--ctimeserialize64"></a><a name="serialize64"></a>CTime::Serialize64  
  
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
 [asctime_s、_wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [_ftime_s、_ftime32_s、_ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)   
 [gmtime_s、_gmtime32_s、_gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s、_localtime32_s、_localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [strftime、wcsftime、_strftime_l、_wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [CTimeSpan クラス](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL と MFC クラスの共有](../../atl-mfc-shared/atl-mfc-shared-classes.md)



