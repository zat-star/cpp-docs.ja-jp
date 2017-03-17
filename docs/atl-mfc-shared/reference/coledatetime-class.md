---
title: "時刻クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDateTime
- ATLCOMTIME/ATL::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::Format
- ATLCOMTIME/ATL::COleDateTime::GetAsDBTIMESTAMP
- ATLCOMTIME/ATL::COleDateTime::GetAsSystemTime
- ATLCOMTIME/ATL::COleDateTime::GetAsUDATE
- ATLCOMTIME/ATL::COleDateTime::GetCurrentTime
- ATLCOMTIME/ATL::COleDateTime::GetDay
- ATLCOMTIME/ATL::COleDateTime::GetDayOfWeek
- ATLCOMTIME/ATL::COleDateTime::GetDayOfYear
- ATLCOMTIME/ATL::COleDateTime::GetHour
- ATLCOMTIME/ATL::COleDateTime::GetMinute
- ATLCOMTIME/ATL::COleDateTime::GetMonth
- ATLCOMTIME/ATL::COleDateTime::GetSecond
- ATLCOMTIME/ATL::COleDateTime::GetStatus
- ATLCOMTIME/ATL::COleDateTime::GetYear
- ATLCOMTIME/ATL::COleDateTime::ParseDateTime
- ATLCOMTIME/ATL::COleDateTime::SetDate
- ATLCOMTIME/ATL::COleDateTime::SetDateTime
- ATLCOMTIME/ATL::COleDateTime::SetStatus
- ATLCOMTIME/ATL::COleDateTime::SetTime
- ATLCOMTIME/ATL::COleDateTime::m_dt
- ATLCOMTIME/ATL::COleDateTime::m_status
dev_langs:
- C++
helpviewer_keywords:
- shared classes, COleDateTime
- time-only values
- Date data type, MFC encapsulation of
- COleDateTime class
- dates, handling in MFC
- time, handling in MFC
ms.assetid: e718f294-16ec-4649-88b6-a4dbae5178fb
caps.latest.revision: 34
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
ms.openlocfilehash: ecb32876e55c9801b28fefa1a189508ffbc8b78c
ms.lasthandoff: 02/24/2017

---
# <a name="coledatetime-class"></a>時刻クラス
カプセル化、 `DATE` OLE オートメーションで使用されているデータ型。  
  
## <a name="syntax"></a>構文  
  
```
class COleDateTime
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleDateTime::COleDateTime](#coledatetime)|`COleDateTime` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[近く](#format)|書式設定された文字列表記を生成、`COleDateTime`オブジェクトです。|  
|[COleDateTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|時刻を取得するには、このメソッドを呼び出して、`COleDateTime`オブジェクトとして、 **DBTIMESTAMP**データ構造体。|  
|[COleDateTime::GetAsSystemTime](#getassystemtime)|時刻を取得するには、このメソッドを呼び出して、`COleDateTime`オブジェクトとして、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)データ構造体。|  
|[COleDateTime::GetAsUDATE](#getasudate)|時刻を取得するには、このメソッドを呼び出して、`COleDateTime`として、 **UDATE**データ構造体。|  
|[COleDateTime::GetCurrentTime](#getcurrenttime)|作成、`COleDateTime`を現在の時刻 (静的メンバー関数) を表すオブジェクト。|  
|[COleDateTime::GetDay](#getday)|この日を返します`COleDateTime`オブジェクトは (1 ~ 31 日) を表します。|  
|[COleDateTime::GetDayOfWeek](#getdayofweek)|この週の曜日を返します`COleDateTime`(日曜日 = 1) を表すオブジェクトします。|  
|[COleDateTime::GetDayOfYear](#getdayofyear)|これで、年の日付を返します`COleDateTime`(1 月 1 日 = 1) を表すオブジェクトします。|  
|[COleDateTime::GetHour](#gethour)|この時間が返されます`COleDateTime`オブジェクトが表す (0 ~ 23)。|  
|[COleDateTime::GetMinute](#getminute)|この分を返します`COleDateTime`オブジェクトが表す (0 ~ 59)。|  
|[COleDateTime::GetMonth](#getmonth)|これで、月を返します`COleDateTime`オブジェクトは (1 ~ 12) を表します。|  
|[COleDateTime::GetSecond](#getsecond)|この 2 つ目が返されます`COleDateTime`オブジェクトが表す (0 ~ 59)。|  
|[「](#getstatus)|この状態 (有効) を取得`COleDateTime`オブジェクトです。|  
|[COleDateTime::GetYear](#getyear)|これは年を返します`COleDateTime`オブジェクトが表す。|  
|[COleDateTime::ParseDateTime](#parsedatetime)|文字列から日付/時刻値を読み取っての値を設定`COleDateTime`します。|  
|[COleDateTime::SetDate](#setdate)|この値を設定`COleDateTime`オブジェクトを指定した日付専用の値にします。|  
|[COleDateTime::SetDateTime](#setdatetime)|この値を設定`COleDateTime`オブジェクトを指定した日付/時刻値にします。|  
|[COleDateTime::SetStatus](#setstatus)|この状態 (有効) を設定`COleDateTime`オブジェクトです。|  
|[COleDateTime::SetTime](#settime)|この値を設定`COleDateTime`オブジェクトを指定された時間のみの値にします。|  
  
### <a name="public-operators"></a>パブリック演算子  

|名前|説明|  
|----------|-----------------|  
|[COleDateTime::operator = =、COleDateTime::operator<,></,>](#coledatetime_relational_operators)|2 つの比較`COleDateTime`値。|  
|[COleDateTime::operator +、- COleDateTime::operator](#operator_add_-)|加算し、減算`COleDateTime`値。|  
|[COleDateTime::operator + =、-= COleDateTime::operator](#operator_add_eq_-_eq)|加算し、減算、`COleDateTime`これから値`COleDateTime`オブジェクトです。|  
|[COleDateTime::operator =](#operator_eq)|コピー、`COleDateTime`値。|  
|[COleDateTime::operator 日付、COleDateTime::operator 日 *](#operator_date)|変換、`COleDateTime`値を`DATE`または`DATE*`です。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleDateTime::m_dt](#m_dt)|基になるを含む**日付**この`COleDateTime`オブジェクトです。|  
|[COleDateTime::m_status](#m_status)|この状態を表す`COleDateTime`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 `COleDateTime`基本クラスはありません。  
  
 使用できる型のいずれか、 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) OLE オートメーションのデータ型。 A`COleDateTime`値は、絶対日付と時刻の値を表します。  
  
 `DATE`浮動小数点値として型を実装します。 午前 0 時に、日は 1899 年 12 月 30 日から計測されます。 次の表は、一部の日付と関連付けられている値を示します。  
  
|日付|値|  
|----------|-----------|  
|1899 年 12 月 29 日午前 0 時|-1.0|  
|1899 年 12 月 29 日午前 6 時|-1.25|  
|1899 年 12 月 30 日の午前 0 時|0.0|  
|1899 年 12 月 31 日の午前 0 時|1.0|  
|1900 年 1 月 1 日午前 6 時|2.25|  
  
> [!CAUTION]
>  上の表では、1899 年 12 月 30 日の午前 0 時前に日付の値が負になる時刻の値れないこと注意してください。 たとえば、午前 6時 00分はかどうかの曜日を表す整数が肯定的 (1899 年 12 月 30 日) の後 (1899 年 12 月 30 日) の前に負の値に関係なく、小数部の値 0.25 で表現されます。 つまり、単純なフローティング ポイントの比較が誤って並べ替えることが、 `COleDateTime` 12/29/1899 として 6時 00分 AM を表す**後**1 よりも、同じ日の午前 7時 00分を表します。  
  
 `COleDateTime`クラスは、100 年 1 月 1 日 12 月 31 日までの日付から 9999 を処理します。 `COleDateTime`クラスはグレゴリオ暦のカレンダーを使用して、ユリウス暦はサポートしていません。 `COleDateTime`夏時間の期間は無視されます。 (参照[日付と時刻: オートメーションによるサポート](../../atl-mfc-shared/date-and-time-automation-support.md))。  
  
> [!NOTE]
>  使用することができます、`%y`形式の日付は 1900 年以降だけ 2 桁の年を取得します。 使用する場合、 `%y` 1900 年より前に、の日付、コードで形式には、アサーション エラーが生成されます。  
  
 この型は、日付だけ、または時間のみの値を表すも使用されます。 規則では、時間のみの値として日付 0 (1899 年 12 月 30 日) を使用し、日付のみの値の時刻 00:00 (午前 0 時) を使用します。  
  
 作成する場合、`COleDateTime`日付を使用して、オブジェクト、日付が、許容されるが、後続の呼び出しを 100 未満`GetYear`、 `GetMonth`、 `GetDay`、 `GetHour`、 `GetMinute`、および`GetSecond`失敗し、-1 を返します。 以前は、2 桁の数字の日付を使用する可能性がありますが、日付が 100 またはでは、MFC 4.2 以降にする必要があります。  
  
 問題を回避するには、4 桁の日付を指定します。 例:  
  
 [!code-cpp[NVC_ATLMFC_Utilities&#1;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_1.cpp)]  
  
 基本的な算術演算、`COleDateTime`値のコンパニオン クラスを使用して[メンバー](../../atl-mfc-shared/reference/coledatetimespan-class.md)します。 `COleDateTimeSpan`値は、時間間隔を定義します。 これらのクラス間のリレーションシップと似ていますが、間[CTime](../../atl-mfc-shared/reference/ctime-class.md)と[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)します。  
  
 詳細については、`COleDateTime`と`COleDateTimeSpan`クラス、記事を参照して[日付と時刻: オートメーションによるサポート](../../atl-mfc-shared/date-and-time-automation-support.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ATLComTime.h  
  
##  <a name="coledatetime_relational_operators"></a>時刻の関係演算子  
 比較演算子です。  
  
```
bool operator==(const COleDateTime& date) const throw();
bool operator!=(const COleDateTime& date) const throw();
bool operator<(const COleDateTime& date) const throw();
bool operator>(const COleDateTime& date) const throw();
bool operator<=(const COleDateTime& date) const throw();
bool operator>=(const COleDateTime& date) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `date`  
 **時刻**と比較するオブジェクト。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  ATLASSERT は&2; つのオペランドのいずれかが有効ではない場合に発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#13;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_2.cpp)]  
  
### <a name="example"></a>例  
 The operators **>=**, **\<=**, **>**, and **<**, will assert if the `COleDateTime` object is set to null.  
  
 [!code-cpp[NVC_ATLMFC_Utilities #&170;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_3.cpp)]  
  
##  <a name="coledatetime"></a>COleDateTime::COleDateTime  
 `COleDateTime` オブジェクトを構築します。  
  
```
COleDateTime() throw();
COleDateTime(const VARIANT& varSrc) throw();
COleDateTime(DATE dtSrc) throw();
COleDateTime(time_t timeSrc) throw();
COleDateTime(__time64_t timeSrc) throw();
COleDateTime(const SYSTEMTIME& systimeSrc) throw();
COleDateTime(const FILETIME& filetimeSrc) throw();

COleDateTime(int nYear,
    int nMonth,
    int nDay,
    int nHour,
    int nMin,
    int nSec) throw();

COleDateTime(WORD wDosDate,
    WORD wDosTime) throw();
COleDateTime(const DBTIMESTAMP& dbts) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dateSrc`  
 既存の`COleDateTime`新しいにコピーされるオブジェクト`COleDateTime`オブジェクトです。  
  
 *varSrc*  
 既存の**VARIANT**データ構造体 (可能性がある、`COleVariant`オブジェクト) 日付/時刻値に変換する ( `VT_DATE`) 新しいにコピーして`COleDateTime`オブジェクトです。  
  
 `dtSrc`  
 日付/時刻 (**日付**) 新しいにコピーされる値`COleDateTime`オブジェクトです。  
  
 `timeSrc`  
 A`time_t`または**_ _time64_t**日付/時刻値に変換され、新しいにコピーされる値`COleDateTime`オブジェクトです。  
  
 *systimeSrc*  
 A`SYSTEMTIME`日付/時刻値に変換され、新しいコピーを構造`COleDateTime`オブジェクトです。  
  
 `filetimeSrc`  
 A`FILETIME`日付/時刻値に変換され、新しいコピーを構造`COleDateTime`オブジェクトです。 注意`FILETIME`世界協定時刻 (UTC) を使用して、結果が表示される場合は、構造のローカル時刻を渡すことがあるためです。 参照してください[ファイル時間](http://msdn.microsoft.com/library/windows/desktop/ms724290)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 新しいにコピーされる日付と時刻の値を示す`COleDateTime`オブジェクトです。  
  
 `wDosDate`, `wDosTime`  
 MS-DOS 日付と時刻の値は、日付/時刻値に変換され、新しい`COleDateTime`オブジェクトです。  
  
 `dbts`  
 参照、 [DBTimeStamp](https://msdn.microsoft.com/library/system.data.oledb.oledbtype)現在の現地時刻を含む構造体。  
  
### <a name="remarks"></a>コメント  
 これらすべてのコンス トラクターが新規作成`COleDateTime`オブジェクトの指定した値に初期化します。 次の表は、日付と時刻の各コンポーネントの有効な範囲を示しています。  
  
|日付/時刻のコンポーネント|有効範囲|  
|--------------------------|-----------------|  
|年|100 – 9999|  
|月|0 – 12|  
|日|0 – 31|  
|時|0 – 23|  
|分|0 – 59|  
|秒|0 – 59|  
  
 日付部分の実際の上限の境界が変化するメモは、月と年のコンポーネントに基づいています。 詳細については、「、 **SetDate**または`SetDateTime`メンバー関数。  
  
 各コンス トラクターの簡単な説明を次に示します。  
  
- `COleDateTime(`**)**を構築、 `COleDateTime` 0 (午前 0 時、30 1899 年 12 月) に初期化されるオブジェクト。  
  
- `COleDateTime(``dateSrc` **)**を構築、 `COleDateTime` 、既存のオブジェクト`COleDateTime`オブジェクトです。  
  
- `COleDateTime(`*varSrc* **)**を構築、`COleDateTime`オブジェクトです。 変換しようと、`VARIANT`構造または[COleVariant](../../mfc/reference/colevariant-class.md)日付/時刻へのオブジェクト ( `VT_DATE`) 値です。 この変換が成功すると、新しいに変換後の値がコピー`COleDateTime`オブジェクトです。 値ではない場合、`COleDateTime`オブジェクトの値が 0 (午前 0 時、30 1899 年 12 月)、その状態は無効にします。  
  
- `COleDateTime(``dtSrc` **)**を構築、`COleDateTime`オブジェクトから、**日付**値。  
  
- `COleDateTime(``timeSrc` **)**を構築、`COleDateTime`オブジェクトから、`time_t`値。  
  
- `COleDateTime(`*systimeSrc* **)**を構築、`COleDateTime`からオブジェクトを`SYSTEMTIME`値。  
  
- `COleDateTime(``filetimeSrc` **)**を構築、`COleDateTime`オブジェクトから、`FILETIME`値。 をクリックします。 注意`FILETIME`世界協定時刻 (UTC) を使用して、結果が表示される場合は、構造のローカル時刻を渡すことがあるためです。 参照してください[ファイル時間](http://msdn.microsoft.com/library/windows/desktop/ms724290)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
- `COleDateTime(``nYear`、 `nMonth`、 `nDay`、 `nHour`、 `nMin`、 `nSec` **)**を構築、`COleDateTime`指定された数値からのオブジェクト。  
  
- `COleDateTime(``wDosDate`、 `wDosTime` **)**を構築、 `COleDateTime` MS-DOS 日付と時刻の値は、指定したオブジェクト。  
  
 詳細については、`time_t`データ型を参照してください、[時間](../../c-runtime-library/reference/time-time32-time64.md)で機能、*ランタイム ライブラリ リファレンス*します。  
  
 詳細については、次を参照してください。、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)と[FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)構造体に、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 境界の詳細については`COleDateTime`値、記事を参照して[日付と時刻: オートメーションによるサポート](../../atl-mfc-shared/date-and-time-automation-support.md)します。  
  
> [!NOTE]
>  コンス トラクターを使用して、 **DBTIMESTAMP**パラメーターは、OLEDB.h が含まれる場合にのみ使用できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#2;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_4.cpp)]  
  
##  <a name="format"></a>近く  
 日付/時刻値の書式設定された表現を作成します。  
  
```
CString Format(DWORD dwFlags = 0,  LCID lcid = LANG_USER_DEFAULT) const;
CString Format(LPCTSTR lpszFormat) const;
CString Format(UINT nFormatID) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `dwFlags`  
 次のロケール フラグのいずれかを示します。  
  
- `LOCALE_NOUSEROVERRIDE`カスタム ユーザー設定の代わりに、システム既定ロケールの設定を使用します。  
  
- `VAR_TIMEVALUEONLY`解析中に、日付部分を無視します。  
  
- `VAR_DATEVALUEONLY`解析中に時刻部分を無視します。  
  
 `lcid`  
 変換に使用するロケール ID を示します。 言語識別子の詳細については、次を参照してください。[言語識別子](http://msdn.microsoft.com/library/windows/desktop/dd318691)します。  
  
 `lpszFormat`  
 書式文字列のような`printf`文字列の書式を設定します。 各パーセントに続くコードの書式設定 ( `%`) 署名と、対応する置き換え`COleDateTime`コンポーネントです。 書式指定文字列内の文字は、返される文字列に変更されていないコピーされます。 ランタイム関数を参照してください[strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)の詳細。 値と書式設定コードの意味`Format`は。  
  
- `%H`現在の日の時間  
  
- `%M`現在の時刻の分  
  
- `%S`現在の時間 (秒)  
  
- `%%`パーセント記号  
  
 `nFormatID`  
 コントロールの書式設定文字列のリソース ID です。  
  
### <a name="return-value"></a>戻り値  
 A`CString`書式設定された日付/時刻値を格納します。  
  
### <a name="remarks"></a>コメント  
 場合はこの状態`COleDateTime`オブジェクトが null、戻り値は空の文字列です。 戻り値の文字列が文字列リソースで指定された状態が有効である場合は、`ATL_IDS_DATETIME_INVALID`です。  
  
 この関数の&3; つの形式の簡単な説明に従います。  
  
 `Format`( `dwFlags`, `lcid`)  
 このフォームは、日付と時刻の言語仕様 (ロケール Id) を使用して値を形式です。 既定のパラメーターを使用して、このフォームで印刷されます、日付と時刻、時刻部分が 0 (午前 0 時)、その場合は日付のみが出力されますかがない限り日付部分では、0 (30 1899 年 12 月)、その場合にだけが出力されます。 日付/時刻値が 0 (30 1899 年 12 月、午前 0 時) の場合は、既定のパラメーターには、このフォームは午前 0 時を印刷します。  
  
 `Format`( `lpszFormat`)  
 この形式でパーセント記号 (%)、末尾に挿入される特別な書式設定コードを含む書式指定文字列を使用して、値を書式化`printf`します。 書式指定文字列は、関数にパラメーターとして渡されます。 書式設定コードの詳細については、次を参照してください。 [strftime、wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)ランタイム ライブラリ リファレンスです。  
  
 `Format`( `nFormatID`)  
 この形式でパーセント記号 (%)、末尾に挿入される特別な書式設定コードを含む書式指定文字列を使用して、値を書式化`printf`します。 書式指定文字列は、リソースです。 この文字列リソースの ID は、パラメーターとして渡されます。 書式設定コードの詳細については、次を参照してください。 [strftime、wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)で、*ランタイム ライブラリ リファレンス*します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#3;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_5.cpp)]  
  
##  <a name="getasdbtimestamp"></a>COleDateTime::GetAsDBTIMESTAMP  
 時刻を取得するには、このメソッドを呼び出して、`COleDateTime`オブジェクトとして、 **DBTIMESTAMP**データ構造体。  
  
```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dbts`  
 参照、 [DBTimeStamp](https://msdn.microsoft.com/library/system.data.oledb.oledbtype)構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 結果として得られる時刻を、参照されている `dbts` 構造体に格納します。 **DBTIMESTAMP**この関数によって初期化データ構造が含まれ、**分数**メンバーがゼロに設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&4;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_6.cpp)]  
  
##  <a name="getassystemtime"></a>COleDateTime::GetAsSystemTime  
 時刻を取得するには、このメソッドを呼び出して、`COleDateTime`オブジェクトとして、`SYSTEMTIME`データ構造体。  
  
```
bool GetAsSystemTime(SYSTEMTIME& sysTime) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *sysTime*  
 参照、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)から変換された日付/時刻値を受け取る、`COleDateTime`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 返します**true**成功した場合。**false** 、変換に失敗した場合、または場合、`COleDateTime`オブジェクトが**NULL**か無効です。  
  
### <a name="remarks"></a>コメント  
 `GetAsSystemTime`参照先の結果として得られる時間を格納*sysTime*オブジェクトです。 `SYSTEMTIME`この関数によって初期化データ構造が含まれ、 **wMilliseconds**メンバーがゼロに設定します。  
  
 参照してください[GetStatus](#getstatus)ステータス情報の詳細についてに保持されているため、`COleDateTime`オブジェクトです。  
  
##  <a name="getasudate"></a>COleDateTime::GetAsUDATE  
 時刻を取得するには、このメソッドを呼び出して、`COleDateTime`オブジェクトとして、 **UDATE**データ構造体。  
  
```
bool GetAsUDATE(UDATE& udate) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `udate`  
 参照、 **UDATE**から変換された日付/時刻値を受け取る、`COleDateTime`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 返します**true**成功した場合。**false** 、変換に失敗した場合、または場合、`COleDateTime`オブジェクトが**NULL**か無効です。  
  
### <a name="remarks"></a>コメント  
 A **UDATE**構造体は、「展開」の日付を表します。  
  
##  <a name="getcurrenttime"></a>COleDateTime::GetCurrentTime  
 現在の日付/時刻値を返すには、この静的メンバー関数を呼び出します。  
  
```
static COleDateTime WINAPI GetCurrentTime() throw();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#5;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_7.cpp)]  
  
##  <a name="getday"></a>COleDateTime::GetDay  
 この日付/時刻値で表される月の日を取得します。  
  
```
int GetDay() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この値によって表される月の日にち`COleDateTime`オブジェクトまたは`COleDateTime::error`場合は、1 日を取得できませんでした。  
  
### <a name="remarks"></a>コメント  
 有効な戻り値の 1 ~ 31 の範囲です。  
  
 この値をクエリする他のメンバー関数について`COleDateTime`オブジェクト、次のメンバー関数を参照してください。  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [曜日](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&6;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_8.cpp)]  
  
##  <a name="getdayofweek"></a>COleDateTime::GetDayOfWeek  
 この日付/時刻値で表される月の日を取得します。  
  
```
int GetDayOfWeek() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この値によって表される曜日`COleDateTime`オブジェクトまたは`COleDateTime::error`場合は、週の曜日を取得できませんでした。  
  
### <a name="remarks"></a>コメント  
 有効な戻り値は 1 ~ 7、範囲、ここで、1 = 日曜日、2 = 月曜日、したりします。  
  
 この値をクエリする他のメンバー関数について`COleDateTime`オブジェクト、次のメンバー関数を参照してください。  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#7;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_9.cpp)]  
  
##  <a name="getdayofyear"></a>COleDateTime::GetDayOfYear  
 この日付/時刻値で表される年間積算日を取得します。  
  
```
int GetDayOfYear() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この値によって表される年間積算日`COleDateTime`オブジェクトまたは`COleDateTime::error`場合は、年の日付を取得できませんでした。  
  
### <a name="remarks"></a>コメント  
 有効な戻り値は 1 ~ 366 の間、1 月 1 日 = 1 です。  
  
 この値をクエリする他のメンバー関数について`COleDateTime`オブジェクト、次のメンバー関数を参照してください。  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [曜日](#getdayofweek)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#8;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_10.cpp)]  
  
##  <a name="gethour"></a>COleDateTime::GetHour  
 この日付/時刻値で表される時間を取得します。  
  
```
int GetHour() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この値によって表される時間`COleDateTime`オブジェクトまたは`COleDateTime::error`場合は、時間を取得できませんでした。  
  
### <a name="remarks"></a>コメント  
 有効な戻り値の 0 から 23 までの範囲です。  
  
 この値をクエリする他のメンバー関数について`COleDateTime`オブジェクト、次のメンバー関数を参照してください。  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [曜日](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#9;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_11.cpp)]  
  
##  <a name="getminute"></a>COleDateTime::GetMinute  
 この日付/時刻値で表される分を取得します。  
  
```
int GetMinute() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この値によって表される分`COleDateTime`オブジェクトまたは`COleDateTime::error`場合は、分単位を取得できませんでした。  
  
### <a name="remarks"></a>コメント  
 有効な戻り値の 0 から 59 までの範囲です。  
  
 この値をクエリする他のメンバー関数について`COleDateTime`オブジェクト、次のメンバー関数を参照してください。  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetSecond](#getsecond)  
  
- [曜日](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>例  
 例を参照してください[GetHour](#gethour)します。  
  
##  <a name="getmonth"></a>COleDateTime::GetMonth  
 この日付/時刻値で表される月を取得します。  
  
```
int GetMonth() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この値で表される月`COleDateTime`オブジェクトまたは`COleDateTime::error`場合は、1 か月を取得できませんでした。  
  
### <a name="remarks"></a>コメント  
 有効な戻り値の 1 から 12 までの範囲。  
  
 この値をクエリする他のメンバー関数について`COleDateTime`オブジェクト、次のメンバー関数を参照してください。  
  
- [GetDay](#getday)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [曜日](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>例  
 例を参照してください[GetDay](#getday)します。  
  
##  <a name="getsecond"></a>COleDateTime::GetSecond  
 この日付/時刻値で表される秒を取得します。  
  
```
int GetSecond() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この値によって表される秒`COleDateTime`オブジェクトまたは`COleDateTime::error`場合は、2 つ目を取得できませんでした。  
  
### <a name="remarks"></a>コメント  
 有効な戻り値の 0 から 59 までの範囲です。  
  
> [!NOTE]
>  `COleDateTime`クラスはうるう秒をサポートしていません。  
  
 実装の詳細については`COleDateTime`、記事を参照して[日付と時刻: オートメーションによるサポート](../../atl-mfc-shared/date-and-time-automation-support.md)します。  
  
 この値をクエリする他のメンバー関数について`COleDateTime`オブジェクト、次のメンバー関数を参照してください。  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [曜日](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>例  
 例を参照してください[GetHour](#gethour)します。  
  
##  <a name="getstatus"></a>「  
 状態 (有効) を取得する指定された`COleDateTime`オブジェクトです。  
  
```
DateTimeStatus GetStatus() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この状態が返されます`COleDateTime`値。 呼び出す場合**GetStatus**上、`COleDateTime`オブジェクトは、既定の構築、戻ります無効です。 呼び出した場合**GetStatus**上、`COleDateTime`は null に設定するコンス トラクターで初期化されたオブジェクト**GetStatus**は null を返します。 参照してください**解説**の詳細。  
  
### <a name="remarks"></a>コメント  
 戻り値は、**返します**列挙型で、内で定義された、`COleDateTime`クラスです。  
  
 `enum DateTimeStatus`  
  
 `{`  
  
 `error = -1,`  
  
 `valid = 0,`  
  
 `invalid = 1,    // Invalid date (out of range, etc.)`  
  
 `null = 2,       // Literally has no value`  
  
 `};`  
  
 これらのステータス値の簡単な説明は、次の一覧を参照してください。  
  
- `COleDateTime::error`日付/時刻値の一部を取得しようとしているときにエラーが発生したことを示します。  
  
- **COleDateTime::valid**ことを示しますがこの`COleDateTime`オブジェクトが無効です。  
  
- **COleDateTime::invalid**ことを示しますがこの`COleDateTime`オブジェクトは無効です。 つまり、その値誤りがあります。  
  
- **COleDateTime::null**ことを示しますがこの`COleDateTime`オブジェクトが null では、このオブジェクトの値が指定されていないことです。 (これは、データベースの意味で「値を持たない、」C++ ではなく"null" **NULL**)。  
  
 状態、`COleDateTime`オブジェクトが無効で、次の場合。  
  
-   値が設定されている場合、 **VARIANT**または`COleVariant`値を日付/時刻値に変換できませんでした。  
  
-   値が設定されている場合、 `time_t`、 `SYSTEMTIME`、または`FILETIME`値を有効な日付/時刻値に変換できませんでした。  
  
-   その値を設定した場合`SetDateTime`無効なパラメーター値を使用します。  
  
-   このオブジェクトが、オーバーフローまたはアンダー フロー代入演算操作中、つまり場合、`+=`または`-=`です。  
  
-   場合は、無効な値は、このオブジェクトに割り当てられました。  
  
-   このオブジェクトの状態が明示的に設定に使用して無効な`SetStatus`です。  
  
 操作の詳細については、無効です。 次のメンバー関数を参照してください状態を設定することがあります。  
  
- [時刻](#coledatetime)  
  
- [SetDateTime](#setdatetime)  
  
- [演算子 +、-](#operator_add_-)  
  
- [演算子 + =、=](#operator_add_eq_-_eq)  
  
 境界の詳細については`COleDateTime`値、記事を参照して[日付と時刻: オートメーションによるサポート](../../atl-mfc-shared/date-and-time-automation-support.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#10;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_12.cpp)]  
  
##  <a name="getyear"></a>COleDateTime::GetYear  
 この日付/時刻値で表される年を取得します。  
  
```
int GetYear() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この値によって表される年間積算`COleDateTime`オブジェクトまたは`COleDateTime::error`場合は、年を取得できませんでした。  
  
### <a name="remarks"></a>コメント  
 有効な戻り値は、世紀を含む 100 ~ 9999 の間の範囲。  
  
 この値をクエリする他のメンバー関数について`COleDateTime`オブジェクト、次のメンバー関数を参照してください。  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [曜日](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 境界の詳細については`COleDateTime`値、記事を参照して[日付と時刻: オートメーションによるサポート](../../atl-mfc-shared/date-and-time-automation-support.md)します。  
  
### <a name="example"></a>例  
 例を参照してください[GetDay](#getday)します。  
  
##  <a name="m_dt"></a>COleDateTime::m_dt  
 基になる**日付**この構造体`COleDateTime`オブジェクトです。  
  
```
DATE m_dt;
```  
  
### <a name="remarks"></a>コメント  
  
> [!CAUTION]
>  値を変更、**日付**この関数によって返されたポインターからアクセスされるオブジェクトはこの値を変更`COleDateTime`オブジェクトです。 このステータスは変更されません`COleDateTime`オブジェクトです。  
  
 実装の詳細については、**日付**オブジェクトは、「[日付と時刻: オートメーションによるサポート](../../atl-mfc-shared/date-and-time-automation-support.md)します。  
  
##  <a name="m_status"></a>COleDateTime::m_status  
 この状態を表す`COleDateTime`オブジェクトです。  
  
```
DateTimeStatus m_status;
```  
  
### <a name="remarks"></a>コメント  
 このデータ メンバーの型は、列挙型**返します**、内で定義されている、`COleDateTime`クラスです。 参照してください[は、「](#getstatus)詳細です。  
  
> [!CAUTION]
>  このデータ メンバーは、高度なプログラミングに適しています。 インライン メンバー関数を使用する必要があります[GetStatus](#getstatus)と[SetStatus](#setstatus)します。 参照してください`SetStatus`このデータ メンバーを明示的に設定に関する注意事項についてさらには。  
  
##  <a name="operator_eq"></a>COleDateTime::operator =  
 コピー、`COleDateTime`値。  
  
```
COleDateTime& operator=(const VARIANT& varSrc) throw();
COleDateTime& operator=(DATE dtSrc) throw();
COleDateTime& operator=(const time_t& timeSrc) throw();
COleDateTime& operator=(const __time64_t& timeSrc) throw();
COleDateTime& operator=(const SYSTEMTIME& systimeSrc) throw();
COleDateTime& operator=(const FILETIME& filetimeSrc) throw();
COleDateTime& operator=(const UDATE& udate) throw();
```  
  
### <a name="remarks"></a>コメント  
 これらのオーバー ロード代入演算子は、このソースの日付/時刻値をコピー`COleDateTime`オブジェクトです。 これらのそれぞれの簡単な説明では、代入演算子のオーバー ロードします。  
  
- **operator = (** `dateSrc` **)**値およびオペランドの状態は、これにコピーされます`COleDateTime`オブジェクトです。  
  
- **演算子 = (** *varSrc* **)**場合の変換、 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)値 (または[COleVariant](../../mfc/reference/colevariant-class.md)オブジェクト) 日付/時刻へ ( `VT_DATE`) が成功すると、変換された値がコピーに`COleDateTime`オブジェクトとその状態は、有効な設定がします。 このオブジェクトの値が 0 (1899 年 12 月 30 日の午前 0 時) に設定して、変換が成功しなかった場合、その状態は無効にします。  
  
- **演算子 = (** `dtSrc` **)** 、**日付**値がこれにコピー`COleDateTime`オブジェクトとその状態は、有効な設定されています。  
  
- **operator = (** `timeSrc` **)** 、`time_t`または**_ _time64_t**値が変換され、これにコピー`COleDateTime`オブジェクトです。 変換が成功した場合は、このオブジェクトの状態に有効な設定です。失敗した場合、設定されているかどうか無効にします。  
  
- **operator = (** *systimeSrc* **)** 、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)値が変換され、これにコピー`COleDateTime`オブジェクトです。 変換が成功した場合は、このオブジェクトの状態に有効な設定です。失敗した場合、設定されているかどうか無効にします。  
  
- **operator = (** `udate` **)** 、 **UDATE**値が変換され、これにコピー`COleDateTime`オブジェクトです。 変換が成功した場合は、このオブジェクトの状態に有効な設定です。失敗した場合、設定されているかどうか無効にします。 A **UDATE**構造体は、「展開」の日付を表します。 この関数を参照してください[VarDateFromUdate](http://msdn.microsoft.com/en-us/1c924ac5-b896-49e1-9ccf-825ac7a030c8)詳細です。  
  
- **operator = (** `filetimeSrc` **)** 、 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)値が変換され、これにコピー`COleDateTime`オブジェクトです。 変換が成功した場合は、このオブジェクトの状態に有効な設定です。それ以外の場合に設定されている無効にします。 `FILETIME`世界協定時刻 (UTC) を使用して、ので、構造体の UTC 時刻を渡すことの結果はローカル時刻を UTC 時刻から変換バリアント時刻として格納されます。 この動作は、Visual C 6.0 および Visual C .NET 2003 SP2 の場合と同じです。 参照してください[ファイル時間](http://msdn.microsoft.com/library/windows/desktop/ms724290)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
 詳細については、次を参照してください。、 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)内のエントリ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 詳細については、`time_t`データ型を参照してください、[時間](../../c-runtime-library/reference/time-time32-time64.md)で機能、*ランタイム ライブラリ リファレンス*します。  
  
 詳細については、次を参照してください。、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)と[FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)構造体に、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 境界の詳細については`COleDateTime`値、記事を参照して[日付と時刻: オートメーションによるサポート](../../atl-mfc-shared/date-and-time-automation-support.md)します。  
  
##  <a name="operator_add_-"></a>COleDateTime::operator +、-  
 加算し、減算**時刻**値。  
  
```
COleDateTime operator+(COleDateTimeSpan dateSpan) const throw();
COleDateTime operator-(COleDateTimeSpan dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTime& date) const throw();
```  
  
### <a name="remarks"></a>コメント  
 `COleDateTime`オブジェクトは、絶対時刻を表します。 [しかし](../../atl-mfc-shared/reference/coledatetimespan-class.md)オブジェクトは、相対時間を表します。 最初の&2; つの演算子では、追加または削除することができる、`COleDateTimeSpan`値から、`COleDateTime`値。 3 番目の演算子では、1 を減算することができます`COleDateTime`を譲渡して別の数値から、`COleDateTimeSpan`値。  
  
 結果の状態は null オペランドのいずれかの場合`COleDateTime`値は null です。  
  
 場合、その結果`COleDateTime`値が許容される値、状態の境界の外側にある`COleDateTime`値が無効です。  
  
 オペランドのいずれかが無効で、もう一方が null でない場合、その結果のステータス`COleDateTime`値が無効です。  
  
 ** + **と** - **演算子はアサート場合、`COleDateTime`オブジェクトが設定を null にします。 参照してください[時刻関係演算子](#coledatetime_relational_operators)例については、です。  
  
 有効、無効、および null 状態の値の詳細については、次を参照してください。、[ついて](#m_status)メンバー変数です。  
  
 境界の詳細については`COleDateTime`値、記事を参照して[日付と時刻: オートメーションによるサポート](../../atl-mfc-shared/date-and-time-automation-support.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#12;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_13.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>COleDateTime::operator + =、=  
 加算し、減算、**時刻**これから値`COleDateTime`オブジェクトです。  
  
```
COleDateTime& operator+=(COleDateTimeSpan dateSpan) throw();
COleDateTime& operator-=(COleDateTimeSpan dateSpan) throw();
```  
  
### <a name="remarks"></a>コメント  
 これらの演算子では、追加または削除することができる、`COleDateTimeSpan`値との間この`COleDateTime`します。 結果の状態は null オペランドのいずれかの場合`COleDateTime`値は null です。  
  
 場合、その結果`COleDateTime`値が許容される値をこの状態の境界の外側にある`COleDateTime`設定は無効にします。  
  
 オペランドのいずれかが無効で、他が null でない場合、その結果のステータス`COleDateTime`値が無効です。  
  
 有効、無効、および null 状態の値の詳細については、次を参照してください。、[ついて](#m_status)メンバー変数です。  
  
 ** += **と** -= **演算子はアサート場合、`COleDateTime`オブジェクトが設定を null にします。 参照してください[時刻関係演算子](#coledatetime_relational_operators)例については、です。  
  
 境界の詳細については`COleDateTime`値、記事を参照して[日付と時刻: オートメーションによるサポート](../../atl-mfc-shared/date-and-time-automation-support.md)します。  
  
##  <a name="operator_date"></a>COleDateTime::operator 日付  
 変換、**時刻**値を**日付**します。  
  
```
operator DATE() const throw();
```  
  
### <a name="remarks"></a>コメント  
 この演算子、**日付**値がこれからコピーしたオブジェクト`COleDateTime`オブジェクトです。 実装の詳細については、**日付**オブジェクトは、「[日付と時刻: オートメーションによるサポート](../../atl-mfc-shared/date-and-time-automation-support.md)します。  
  
 **日付**演算子はアサート場合、`COleDateTime`オブジェクトが設定を null にします。 参照してください[時刻関係演算子](#coledatetime_relational_operators)例については、です。  
  
##  <a name="parsedatetime"></a>COleDateTime::ParseDateTime  
 日付/時刻値を読み取るための文字列を解析します。  
  
```
bool ParseDateTime(  
 LPCTSTR lpszDate,
 DWORD dwFlags = 0,
 LCID lcid = LANG_USER_DEFAULT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszDate`  
 解析するには null で終わる文字列へのポインター。 詳細については、「解説」を参照してください。  
  
 `dwFlags`  
 ロケールの設定と解析フラグを示します。 1 つ以上の次のフラグ:  
  
- **LOCALE_NOUSEROVERRIDE**カスタム ユーザー設定ではなく、システム既定ロケール設定を使用します。  
  
- **VAR_TIMEVALUEONLY**解析中に、日付部分を無視します。  
  
- **VAR_DATEVALUEONLY**解析中に時刻部分を無視します。  
  
 `lcid`  
 変換に使用するロケール ID を示します。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**場合、文字列が正常に変換された日付/時刻値をそれ以外の場合**false**します。  
  
### <a name="remarks"></a>コメント  
 文字列が日付/時刻へ正常に変換された場合の値、この値`COleDateTime`オブジェクトが有効な値とする状態に設定します。  
  
> [!NOTE]
>  年の値は 100 ~ 9999 の範囲でなければなりません。  
  
 `lpszDate`パラメーターは、さまざまな形式を取ることができます。 たとえば、次の文字列には、許容される日付/時刻書式が含まれます。  
  
 `"25 January 1996"`  
  
 `"8:30:00"`  
  
 `"20:30:00"`  
  
 `"January 25, 1996 8:30:00"`  
  
 `"8:30:00 Jan. 25, 1996"`  
  
 `"1/25/1996 8:30:00"  // always specify the full year,`  
  
 `// even in a 'short date' format`  
  
 ロケール ID は、文字列の形式は日付/時刻値に変換できるかどうかにもに影響することに注意してください。  
  
 場合に**VAR_DATEVALUEONLY**時間、0 または午前 0 時に値を設定するとき。 場合に**VAR_TIMEVALUEONLY**日付の値が日付 0、つまり 30 1899 年 12 月に設定します。  
  
 文字列を日付/時刻値に変換されませんでしたか、数値オーバーフローのこの状態が発生した場合`COleDateTime`オブジェクトが無効です。  
  
 境界との実装の詳細については`COleDateTime`値、記事を参照して[日付と時刻: オートメーションによるサポート](../../atl-mfc-shared/date-and-time-automation-support.md)します。  
  
##  <a name="setdate"></a>COleDateTime::SetDate  
 この日付が設定`COleDateTime`オブジェクトです。  
  
```
int SetDate(  
 int nYear,
 int nMonth,
 int nDay) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nYear`、`nMonth`、`nDay`  
 これにコピーされる日付の構成要素を示す`COleDateTime`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 場合は 0 の値`COleDateTime`オブジェクトが設定されました。 そうしないと、1 です。 この戻り値がに基づいて、**返します**列挙型。 詳細については、次を参照してください。、 [SetStatus](#setstatus)メンバー関数。  
  
### <a name="remarks"></a>コメント  
 日付は、指定した値に設定します。 時間は、時間 0、午前 0 時に設定されます。  
  
 パラメーター値の範囲は次の表を参照してください。  
  
|パラメーター|境界|  
|---------------|------------|  
|`nYear`|100 – 9999|  
|`nMonth`|1 – 12|  
|`nDay`|0 – 31|  
  
 月の日がオーバーフローした場合は、次の月と月の正しい日付に変換や、年がインクリメントされます。 日付の値は&0; では、前の月の最終日を示します。 動作は同じ`SystemTimeToVariantTime`します。  
  
 このオブジェクトの状態が に設定されている場合は、パラメーターで指定された日付の値が有効でない**COleDateTime::invalid**します。 使用する必要があります[GetStatus](#getstatus)の有効性を確認、**日付**値し、を想定しないでくださいの値[m_dt](#m_dt)は変更されません。  
  
 日付値の例を次に示します。  
  
|`nYear`|`nMonth`|`nDay`|値|  
|-------------|--------------|------------|-----------|  
|2000|2|29|2000 年 2 月の 29|  
|1776|7|4|1776 年 7 月 4 日|  
|1925|4|35|35 年 1925年 4 月 (無効な日付)|  
|10000|1|1|1 月 1 日 10000 (無効な日付)|  
  
 日付と時刻の両方を設定するを参照してください。 [COleDateTime::SetDateTime](#setdatetime)します。  
  
 この値をクエリするメンバー関数について`COleDateTime`オブジェクト、次のメンバー関数を参照してください。  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [曜日](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 境界の詳細については`COleDateTime`値、記事を参照して[日付と時刻: オートメーションによるサポート](../../atl-mfc-shared/date-and-time-automation-support.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#11;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_14.cpp)]  
  
##  <a name="setdatetime"></a>COleDateTime::SetDateTime  
 この日時設定`COleDateTime`オブジェクトです。  
  
```
int SetDateTime(  
 int nYear,
 int nMonth,
 int nDay,
 int nHour,
 int nMin,
 int nSec) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 これにコピーされる日付と時刻のコンポーネントを示す`COleDateTime`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 場合は 0 の値`COleDateTime`オブジェクトが設定されました。 そうしないと、1 です。 この戻り値がに基づいて、**返します**列挙型。 詳細については、次を参照してください。、 [SetStatus](#setstatus)メンバー関数。  
  
### <a name="remarks"></a>コメント  
 パラメーター値の範囲は次の表を参照してください。  
  
|パラメーター|境界|  
|---------------|------------|  
|`nYear`|100 – 9999|  
|`nMonth`|1 – 12|  
|`nDay`|0 – 31|  
|`nHour`|0 – 23|  
|`nMin`|0 – 59|  
|`nSec`|0 – 59|  
  
 月の日がオーバーフローした場合は、次の月と月の正しい日付に変換や、年がインクリメントされます。 日付の値は&0; では、前の月の最終日を示します。 動作は同じ[SystemTimeToVariantTime](http://msdn.microsoft.com/en-us/d9d69521-9b33-4fc5-8a1c-929f216db450)します。  
  
 パラメーターで指定された日付または時刻の値は有効ですが、このオブジェクトの状態が無効で、このオブジェクトの値に設定がない場合は変更されません。  
  
 時刻値のいくつかの例を次に示します。  
  
|`nHour`|`nMin`|`nSec`|値|  
|-------------|------------|------------|-----------|  
|1|3|3|01:03:03|  
|23|45|0|23:45:00|  
|25|30|0|無効|  
|9|60|0|無効|  
  
 日付値の例を次に示します。  
  
|`nYear`|`nMonth`|`nDay`|値|  
|-------------|--------------|------------|-----------|  
|1995|4|15|1995 年 4 月 15日|  
|1789|7|14|年 7 月の 17 年|  
|1925|2|30|無効|  
|10000|1|1|無効|  
  
 日付のみを設定するを参照してください。 [COleDateTime::SetDate](#setdate)します。 時刻のみを設定するを参照してください。 [COleDateTime::SetTime](#settime)します。  
  
 この値をクエリするメンバー関数について`COleDateTime`オブジェクト、次のメンバー関数を参照してください。  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [曜日](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 境界の詳細については`COleDateTime`値、記事を参照して[日付と時刻: オートメーションによるサポート](../../atl-mfc-shared/date-and-time-automation-support.md)します。  
  
### <a name="example"></a>例  
 例を参照してください[GetStatus](#getstatus)します。  
  
##  <a name="setstatus"></a>COleDateTime::SetStatus  
 この状態を設定`COleDateTime`オブジェクトです。  
  
```
void SetStatus(DateTimeStatus status) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *status*  
 この新しいステータス値`COleDateTime`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 *ステータス*でパラメーターの値が定義されている、**返します**列挙型で、内で定義された、`COleDateTime`クラスです。 参照してください[は、「](#getstatus)詳細です。  
  
> [!CAUTION]
>  この関数は、高度なプログラミングに適しています。 この関数では、このオブジェクトのデータは変更されません。 多くの場合、ステータスを設定する使用となり、`null`または**無効な**です。 注意してください、代入演算子 ([演算子 =](#eq)) と[SetDateTime](#setdatetime)ソース値に基づいて、オブジェクトの状態を設定しないでください。  
  
### <a name="example"></a>例  
 例を参照してください[GetStatus](#getstatus)します。  
  
##  <a name="settime"></a>COleDateTime::SetTime  
 この時間を設定`COleDateTime`オブジェクトです。  
  
```
int SetTime(  
 int nHour,
 int nMin,
 int nSec) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nHour`、`nMin`、`nSec`  
 これにコピーされる時のコンポーネントを示す`COleDateTime`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 場合は 0 の値`COleDateTime`オブジェクトが設定されました。 そうしないと、1 です。 この戻り値がに基づいて、**返します**列挙型。 詳細については、次を参照してください。、 [SetStatus](#setstatus)メンバー関数。  
  
### <a name="remarks"></a>コメント  
 時間は、指定された値に設定されます。 日付は、日付 0、つまり 30 1899 年 12 月に設定されます。  
  
 パラメーター値の範囲は次の表を参照してください。  
  
|パラメーター|境界|  
|---------------|------------|  
|`nHour`|0 – 23|  
|`nMin`|0 – 59|  
|`nSec`|0 – 59|  
  
 パラメーターで指定された値が有効でない時間このオブジェクトの状態が無効で、このオブジェクトの値に設定されている場合は変更されません。  
  
 時刻値のいくつかの例を次に示します。  
  
|`nHour`|`nMin`|`nSec`|値|  
|-------------|------------|------------|-----------|  
|1|3|3|01:03:03|  
|23|45|0|23:45:00|  
|25|30|0|無効|  
|9|60|0|無効|  
  
 日付と時刻の両方を設定するを参照してください。 [COleDateTime::SetDateTime](#setdatetime)します。  
  
 この値をクエリするメンバー関数について`COleDateTime`オブジェクト、次のメンバー関数を参照してください。  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [曜日](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 境界の詳細については`COleDateTime`値、記事を参照して[日付と時刻: オートメーションによるサポート](../../atl-mfc-shared/date-and-time-automation-support.md)します。  
  
### <a name="example"></a>例  
 例を参照してください[SetDate](#setdate)します。  
  
## <a name="see-also"></a>関連項目  
 [COleVariant クラス](../../mfc/reference/colevariant-class.md)   
 [CTime クラス](../../atl-mfc-shared/reference/ctime-class.md)   
 [CTimeSpan クラス](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL と MFC クラスの共有](../../atl-mfc-shared/atl-mfc-shared-classes.md)




