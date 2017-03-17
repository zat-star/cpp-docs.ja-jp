---
title: "|Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::Format
- ATLCOMTIME/ATL::COleDateTimeSpan::GetDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::GetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::SetDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::SetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::m_span
- ATLCOMTIME/ATL::COleDateTimeSpan::m_status
dev_langs:
- C++
helpviewer_keywords:
- timespan
- time span
- shared classes, COleDateTimeSpan
- Date data type, MFC encapsulation of
- COleDateTimeSpan class
ms.assetid: 7441526d-a30a-4019-8fb3-3fee6f897cbe
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4091ca2c766d56d8398119413778af0a0405b8ab
ms.lasthandoff: 02/24/2017

---
# <a name="coledatetimespan-class"></a>メンバー クラス
相対的な時間、時間間隔を表します。  
  
## <a name="syntax"></a>構文  
  
```
class COleDateTimeSpan
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleDateTimeSpan::COleDateTimeSpan](#coledatetimespan)|`COleDateTimeSpan` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleDateTimeSpan::Format](#format)|書式設定された文字列表記を生成、`COleDateTimeSpan`オブジェクトです。|  
|[COleDateTimeSpan::GetDays](#getdays)|この範囲の日付部分を返す`COleDateTimeSpan`オブジェクトが表す。|  
|[COleDateTimeSpan::GetHours](#gethours)|この範囲の時間の部分を返します`COleDateTimeSpan`オブジェクトが表す。|  
|[COleDateTimeSpan::GetMinutes](#getminutes)|この期間の分の部分を返します`COleDateTimeSpan`オブジェクトが表す。|  
|[COleDateTimeSpan::GetSeconds](#getseconds)|この範囲の&2; 番目の部分を返します`COleDateTimeSpan`オブジェクトが表す。|  
|[COleDateTimeSpan::GetStatus](#getstatus)|この状態 (有効) を取得`COleDateTimeSpan`オブジェクトです。|  
|[COleDateTimeSpan::GetTotalDays](#gettotaldays)|この日数を返します`COleDateTimeSpan`オブジェクトが表す。|  
|[COleDateTimeSpan::GetTotalHours](#gettotalhours)|この時間数を返す`COleDateTimeSpan`オブジェクトが表す。|  
|[COleDateTimeSpan::GetTotalMinutes](#gettotalminutes)|この分の数を返します`COleDateTimeSpan`オブジェクトが表す。|  
|[COleDateTimeSpan::GetTotalSeconds](#gettotalseconds)|この秒数を返す`COleDateTimeSpan`オブジェクトが表す。|  
|[COleDateTimeSpan::SetDateTimeSpan](#setdatetimespan)|この値を設定`COleDateTimeSpan`オブジェクトです。|  
|[COleDateTimeSpan::SetStatus](#setstatus)|この状態 (有効) を設定`COleDateTimeSpan`オブジェクトです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|||  
|-|-|  
|[演算子 +、-](#operator_add_-)|追加、減算、および変更するために符号`COleDateTimeSpan`値。|  
|[演算子 + =、=](#operator_add_eq_-_eq)|加算し、減算、`COleDateTimeSpan`これから値`COleDateTimeSpan`値。|  
|[演算子 =](#operator_eq)|コピー、`COleDateTimeSpan`値。|  
|[演算子 = =、<,></,><>](#coledatetimespan_relational_operators)|2 つの比較`COleDateTimeSpan`値。|  
|[演算子 double](#operator_double)|この変換`COleDateTimeSpan`値を**二重**します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleDateTimeSpan::m_span](#m_span)|基になるを含む**二重**この`COleDateTimeSpan`オブジェクトです。|  
|[COleDateTimeSpan::m_status](#m_status)|この状態を表す`COleDateTimeSpan`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 `COleDateTimeSpan`基本クラスはありません。  
  
 A`COleDateTimeSpan`日の時間を維持します。  
  
 `COleDateTimeSpan`そのコンパニオン クラスと共に使用される[時刻](../../atl-mfc-shared/reference/coledatetime-class.md)します。 `COleDateTime`カプセル化、**日付**OLE オートメーションのデータ型。 `COleDateTime`絶対時刻の値を表します。 すべて`COleDateTime`計算が含まれる`COleDateTimeSpan`値。 これらのクラス間の関係は、1 つの間に似ています[CTime](../../atl-mfc-shared/reference/ctime-class.md)と[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)します。  
  
 詳細については、`COleDateTime`と`COleDateTimeSpan`クラス、記事を参照して[日付と時刻: オートメーションによるサポート](../../atl-mfc-shared/date-and-time-automation-support.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ATLComTime.h  
  
##  <a name="coledatetimespan_relational_operators"></a>メンバーの関係演算子  
 比較演算子です。  
  
```
bool operator==(const COleDateTimeSpan& dateSpan) const throw();
bool operator!=(const COleDateTimeSpan& dateSpan) const throw();
bool operator<(const COleDateTimeSpan& dateSpan) const throw();
bool operator>(const COleDateTimeSpan& dateSpan) const throw();
bool operator<=(const COleDateTimeSpan& dateSpan) const throw();
bool operator>=(const COleDateTimeSpan& dateSpan) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *dateSpan*  
 比較対象の `COleDateTimeSpan`。  
  
### <a name="return-value"></a>戻り値  
 これらの演算子は&2; つの日付、期間値を比較し、 **true**条件が true、それ以外の場合**false**します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  ATLASSERT がいずれかのオペランドが無効である場合に発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#25;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_1.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities #&26;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_2.cpp)]  
  
##  <a name="coledatetimespan"></a>COleDateTimeSpan::COleDateTimeSpan  
 `COleDateTimeSpan` オブジェクトを構築します。  
  
```
COleDateTimeSpan() throw();
COleDateTimeSpan(double dblSpanSrc) throw();
COleDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dblSpanSrc`  
 新しいにコピーされる日数`COleDateTimeSpan`オブジェクトです。  
  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 新しいにコピーされる日付と時刻の値を示す`COleDateTimeSpan`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 これらのコンス トラクターのいずれも新しい作成`COleDateTimeSpan`オブジェクトの指定した値に初期化します。 これらのコンス トラクターのそれぞれの簡単な説明が続きます。  
  
- **しかし ()**を構築、`COleDateTimeSpan`を 0 に初期化されるオブジェクト。  
  
- **しかし (** `dblSpanSrc` **)**を構築、`COleDateTimeSpan`オブジェクトと浮動小数点値。  
  
- **しかし (** `lDays` **、** `nHours` **、** `nMins` **、** `nSecs` **)**を構築、`COleDateTimeSpan`オブジェクトは指定された数値に初期化します。  
  
 新しいステータス`COleDateTimeSpan`オブジェクトが、有効な設定です。  
  
 境界の詳細については`COleDateTimeSpan`値、記事を参照して[日付と時刻: オートメーションによるサポート](../../atl-mfc-shared/date-and-time-automation-support.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#14;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_3.cpp)]  
  
##  <a name="format"></a>COleDateTimeSpan::Format  
 書式設定された文字列表記を生成、`COleDateTimeSpan`オブジェクトです。  
  
```
CString Format(LPCTSTR pFormat) const;
CString Format(UINT nID) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `pFormat`  
 書式文字列のような`printf`文字列の書式を設定します。 割合に続くコードの書式設定 ( `%`) 署名、削除され、対応する、`COleDateTimeSpan`コンポーネントです。 書式指定文字列内の文字は、返される文字列に変更されていないコピーされます。 値と書式設定コードの意味**形式**以下に示します。  
  
- **%H**現在の日の時間  
  
- **%M**現在の時間の分数  
  
- **%S**現在の時間 (秒)  
  
- **%%**パーセント記号  
  
 上に示した&4; つの形式は、形式が許容する唯一のコードです。  
  
-  
  
 `nID`  
 コントロールの書式設定文字列のリソース ID です。  
  
### <a name="return-value"></a>戻り値  
 A`CString`書式設定された日付、期間値を格納します。  
  
### <a name="remarks"></a>コメント  
 時間間隔の値の書式設定された表現を作成するこれらの関数を呼び出します。 場合はこの状態`COleDateTimeSpan`オブジェクトが null、戻り値は空の文字列です。 戻り値の文字列が文字列リソースで指定された状態が有効である場合は、**設定されている**します。  
  
 この関数の形式の簡単な説明に従います。  
  
 **Format(** `pFormat` **)**  
 この形式でパーセント記号 (%)、末尾に挿入される特別な書式設定コードを含む書式指定文字列を使用して値を書式化`printf`します。 書式指定文字列は、関数にパラメーターとして渡されます。  
  
 **Format(** `nID` **)**  
 この形式でパーセント記号 (%)、末尾に挿入される特別な書式設定コードを含む書式指定文字列を使用して値を書式化`printf`します。 書式指定文字列は、リソースです。 この文字列リソースの ID は、パラメーターとして渡されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#15;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_4.cpp)]  
  
##  <a name="getdays"></a>COleDateTimeSpan::GetDays  
 この日付、期間値の日付の部分を取得します。  
  
```
LONG GetDays() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この日付、期間値の日の部分です。  
  
### <a name="remarks"></a>コメント  
 戻り値は、約 – この関数の範囲から 3,615,000 と 3,615,000 します。  
  
 その他の関数の値をクエリで、`COleDateTimeSpan`オブジェクト、次のメンバー関数を参照してください。  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [誤差](#gettotaldays)  
  
- [従来](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#16;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_5.cpp)]  
  
##  <a name="gethours"></a>COleDateTimeSpan::GetHours  
 この日付、期間値の時間の部分を取得します。  
  
```
LONG GetHours() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この日付、期間値の時間部分です。  
  
### <a name="remarks"></a>コメント  
 – 23 ~ 23 の間には、この関数範囲からの戻り値。  
  
 その他の関数の値をクエリで、`COleDateTimeSpan`オブジェクト、次のメンバー関数を参照してください。  
  
- [GetDays](#getdays)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [誤差](#gettotaldays)  
  
- [従来](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&17;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_6.cpp)]  
  
##  <a name="getminutes"></a>COleDateTimeSpan::GetMinutes  
 この日付、期間値の分の部分を取得します。  
  
```
LONG GetMinutes() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この日付、期間値の分の部分です。  
  
### <a name="remarks"></a>コメント  
 – 59 ~ 59 の間には、この関数範囲からの戻り値。  
  
 その他の関数の値をクエリで、`COleDateTimeSpan`オブジェクト、次のメンバー関数を参照してください。  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetSeconds](#getseconds)  
  
- [誤差](#gettotaldays)  
  
- [従来](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#18;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_7.cpp)]  
  
##  <a name="getseconds"></a>COleDateTimeSpan::GetSeconds  
 この日付、期間値の&2; 番目の部分を取得します。  
  
```
LONG GetSeconds() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この日付、期間値の秒の部分です。  
  
### <a name="remarks"></a>コメント  
 – 59 ~ 59 の間には、この関数範囲からの戻り値。  
  
 その他の関数の値をクエリで、`COleDateTimeSpan`オブジェクト、次のメンバー関数を参照してください。  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [誤差](#gettotaldays)  
  
- [従来](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#19;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_8.cpp)]  
  
##  <a name="getstatus"></a>COleDateTimeSpan::GetStatus  
 この状態 (有効) を取得`COleDateTimeSpan`オブジェクトです。  
  
```
DateTimeSpanStatus GetStatus() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 このステータス`COleDateTimeSpan`値。  
  
### <a name="remarks"></a>コメント  
 戻り値は、 **DateTimeSpanStatus**列挙型で、内で定義された、`COleDateTimeSpan`クラスです。  
  
 `enum DateTimeSpanStatus{`  
  
 `valid = 0,`  
  
 `invalid = 1,`  
  
 `null = 2,`  
  
 `};`  
  
 これらのステータス値の簡単な説明は、次の一覧を参照してください。  
  
- **COleDateTimeSpan::valid**ことを示しますがこの`COleDateTimeSpan`オブジェクトが無効です。  
  
- **COleDateTimeSpan::invalid**ことを示しますがこの`COleDateTimeSpan`オブジェクトは無効です。 つまり、その値誤りがあります。  
  
- **COleDateTimeSpan::null**ことを示しますがこの`COleDateTimeSpan`オブジェクトが null では、このオブジェクトの値が指定されていないことです。 (これは、データベースの意味で「値を持たない、」C++ ではなく"null" **NULL**)。  
  
 状態、`COleDateTimeSpan`オブジェクトが無効で、次の場合。  
  
-   このオブジェクトが、オーバーフローまたはアンダー フロー代入演算操作中、つまり場合、`+=`または`-=`です。  
  
-   場合は、無効な値は、このオブジェクトに割り当てられました。  
  
-   このオブジェクトの状態が明示的に設定に使用して無効な`SetStatus`です。  
  
 無効な状態を設定することがありますのある操作の詳細については、次を参照してください。 [COleDateTimeSpan::operator +、-](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-)と[COleDateTimeSpan::operator + =、-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq)です。  
  
 境界の詳細については`COleDateTimeSpan`値、記事を参照して[日付と時刻: オートメーションによるサポート](../../atl-mfc-shared/date-and-time-automation-support.md)します。  
  
##  <a name="gettotaldays"></a>COleDateTimeSpan::GetTotalDays  
 この日数で表される日付、期間の値を取得します。  
  
```
double GetTotalDays() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この日付、期間値で表される日数を返します。 この関数は、double 型の値を返すようにプロトタイプ宣言は、整数値を返すことは常にします。  
  
### <a name="remarks"></a>コメント  
 3.65e6 と 3.65e6 約 – この関数の範囲からの戻り値。  
  
 その他の関数の値をクエリで、`COleDateTimeSpan`オブジェクト、次のメンバー関数を参照してください。  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [従来](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#20;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_9.cpp)]  
  
##  <a name="gettotalhours"></a>COleDateTimeSpan::GetTotalHours  
 時間単位にこの日付、期間値を取得します。  
  
```
double GetTotalHours() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この日付、期間は、時間単位で表される値です。 この関数は、double 型の値を返すようにプロトタイプ宣言は、整数値を返すことは常にします。  
  
### <a name="remarks"></a>コメント  
 8.77e7 と 8.77e7 約 – この関数の範囲からの戻り値。  
  
 その他の関数の値をクエリで、`COleDateTimeSpan`オブジェクト、次のメンバー関数を参照してください。  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [誤差](#gettotaldays)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>例  
 例を参照してください[誤差](#gettotaldays)します。  
  
##  <a name="gettotalminutes"></a>COleDateTimeSpan::GetTotalMinutes  
 この日付、期間値を分単位で表現を取得します。  
  
```
double GetTotalMinutes() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この日付、期間値で表される分数を返します。 この関数は、double 型の値を返すようにプロトタイプ宣言は、整数値を返すことは常にします。  
  
### <a name="remarks"></a>コメント  
 5.26e9 と 5.26e9 約 – この関数の範囲からの戻り値。  
  
 その他の関数の値をクエリで、`COleDateTimeSpan`オブジェクト、次のメンバー関数を参照してください。  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [誤差](#gettotaldays)  
  
- [従来](#gettotalhours)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>例  
 例を参照してください[誤差](#gettotaldays)します。  
  
##  <a name="gettotalseconds"></a>COleDateTimeSpan::GetTotalSeconds  
 この日付、期間値 (秒) を取得します。  
  
```
double GetTotalSeconds() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この日付、期間値 (秒) を返します。 この関数は、double 型の値を返すようにプロトタイプ宣言は、整数値を返すことは常にします。  
  
### <a name="remarks"></a>コメント  
 この関数の戻り値の範囲の間で約 – 3.16e11 に 3.16e11 です。  
  
 その他の関数の値をクエリで、`COleDateTimeSpan`オブジェクト、次のメンバー関数を参照してください。  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [誤差](#gettotaldays)  
  
- [従来](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
### <a name="example"></a>例  
 例を参照してください[誤差](#gettotaldays)します。  
  
##  <a name="m_span"></a>COleDateTimeSpan::m_span  
 基になる**二重**値`COleDateTime`オブジェクトです。  
  
```
double m_span;
```  
  
### <a name="remarks"></a>コメント  
 この値は、日の日付/期間を表します。  
  
> [!CAUTION]
>  値を変更、**二重**データ メンバーはこの値を変更`COleDateTimeSpan`オブジェクトです。 このステータスは変更されません`COleDateTimeSpan`オブジェクトです。  
  
##  <a name="m_status"></a>COleDateTimeSpan::m_status  
 このデータ メンバーの型は、列挙型**DateTimeSpanStatus**、内で定義されている、`COleDateTimeSpan`クラスです。  
  
```
DateTimeSpanStatus m_status;
```  
  
### <a name="remarks"></a>コメント  
 `enum DateTimeSpanStatus{`  
  
 `valid = 0,`  
  
 `invalid = 1,`  
  
 `null = 2,`  
  
 `};`  
  
 これらのステータス値の簡単な説明は、次の一覧を参照してください。  
  
- **COleDateTimeSpan::valid**ことを示しますがこの`COleDateTimeSpan`オブジェクトが無効です。  
  
- **COleDateTimeSpan::invalid**ことを示しますがこの`COleDateTimeSpan`オブジェクトは無効です。 つまり、その値誤りがあります。  
  
- **COleDateTimeSpan::null**ことを示しますがこの`COleDateTimeSpan`オブジェクトが null では、このオブジェクトの値が指定されていないことです。 (これは、データベースの意味で「値を持たない、」C++ ではなく"null" **NULL**)。  
  
 状態、`COleDateTimeSpan`オブジェクトが無効で、次の場合。  
  
-   このオブジェクトが、オーバーフローまたはアンダー フロー代入演算操作中、つまり場合、`+=`または`-=`です。  
  
-   場合は、無効な値は、このオブジェクトに割り当てられました。  
  
-   このオブジェクトの状態が明示的に設定に使用して無効な[SetStatus](#setstatus)します。  
  
 無効な状態を設定することがありますのある操作の詳細については、次を参照してください。 [COleDateTimeSpan::operator +、-](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-)と[COleDateTimeSpan::operator + =、-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq)です。  
  
> [!CAUTION]
>  このデータ メンバーは、高度なプログラミングに適しています。 インライン メンバー関数を使用する必要があります[GetStatus](#getstatus)と[SetStatus](#setstatus)します。 参照してください`SetStatus`このデータ メンバーを明示的に設定に関する注意事項についてさらには。  
  
 境界の詳細については`COleDateTimeSpan`値、記事を参照して[日付と時刻: オートメーションによるサポート](../../atl-mfc-shared/date-and-time-automation-support.md)します。  
  
##  <a name="operator_eq"></a>COleDateTimeSpan::operator =  
 コピー、`COleDateTimeSpan`値。  
  
```
COleDateTimeSpan& operator=(double dblSpanSrc) throw();
```  
  
### <a name="remarks"></a>コメント  
 このオーバー ロード代入演算子は、これにソースの日付、期間値をコピー`COleDateTimeSpan`オブジェクトです。  
  
##  <a name="operator_add_-"></a>COleDateTimeSpan::operator +、-  
 追加、減算、および変更するために符号`COleDateTimeSpan`値。  
  
```
COleDateTimeSpan operator+(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-() const throw();
```  
  
### <a name="remarks"></a>コメント  
 最初の&2; つの演算子では、追加し、日付、期間値を減算します。 3 つ目では、日付、期間値の符号を変更できます。  
  
 結果の状態は null オペランドのいずれかの場合`COleDateTimeSpan`値は null です。  
  
 オペランドのいずれかが無効で、もう一方が null でない場合、その結果のステータス`COleDateTimeSpan`値が無効です。  
  
 有効、無効、および null 状態の値の詳細については、次を参照してください。、[ついて](#m_status)メンバー変数です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities 第&23;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_10.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>COleDateTimeSpan::operator + =、=  
 加算し、減算、`COleDateTimeSpan`これから値`COleDateTimeSpan`値。  
  
```
COleDateTimeSpan& operator+=(const COleDateTimeSpan dateSpan) throw();
COleDateTimeSpan& operator-=(const COleDateTimeSpan dateSpan) throw();
```  
  
### <a name="remarks"></a>コメント  
 これらの演算子を使用すると、追加し、これからの日付、期間値を減算`COleDateTimeSpan`オブジェクトです。 結果の状態は null オペランドのいずれかの場合`COleDateTimeSpan`値は null です。  
  
 オペランドのいずれかが無効で、もう一方が null でない場合、その結果のステータス`COleDateTimeSpan`値が無効です。  
  
 有効、無効、および null 状態の値の詳細については、次を参照してください。、[ついて](#m_status)メンバー変数です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&24;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_11.cpp)]  
  
##  <a name="operator_double"></a>二重 COleDateTimeSpan::operator  
 この変換`COleDateTimeSpan`値を**二重**します。  
  
```
operator double() const throw();
```  
  
### <a name="remarks"></a>コメント  
 この演算子は、この値を返します。`COleDateTimeSpan`日間の浮動小数点数としての値。  
  
##  <a name="setdatetimespan"></a>COleDateTimeSpan::SetDateTimeSpan  
 この日付、期間の値を設定します。  
  
```
void SetDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 これにコピーされる日付範囲と時間間隔の値を示す`COleDateTimeSpan`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 関数の値をクエリで、`COleDateTimeSpan`オブジェクト、次のメンバー関数を参照してください。  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [誤差](#gettotaldays)  
  
- [従来](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&21;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_12.cpp)]  
  
##  <a name="setstatus"></a>COleDateTimeSpan::SetStatus  
 この状態 (有効) を設定`COleDateTimeSpan`オブジェクトです。  
  
```
void SetStatus(DateTimeSpanStatus status) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *status*  
 この新しいステータス値`COleDateTimeSpan`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 *ステータス*でパラメーターの値が定義されている、 **DateTimeSpanStatus**列挙型で、内で定義された、`COleDateTimeSpan`クラスです。  
  
 `enum DateTimeSpanStatus{`  
  
 `valid = 0,`  
  
 `invalid = 1,`  
  
 `null = 2,`  
  
 `};`  
  
 これらのステータス値の簡単な説明は、次の一覧を参照してください。  
  
- **COleDateTimeSpan::valid**ことを示しますがこの`COleDateTimeSpan`オブジェクトが無効です。  
  
- **COleDateTimeSpan::invalid**ことを示しますがこの`COleDateTimeSpan`オブジェクトは無効です。 つまり、その値誤りがあります。  
  
- **COleDateTimeSpan::null**ことを示しますがこの`COleDateTimeSpan`オブジェクトが null では、このオブジェクトの値が指定されていないことです。 (これは、データベースの意味で「値を持たない、」C++ ではなく"null" **NULL**)。  
  
    > [!CAUTION]
    >  この関数は、高度なプログラミングに適しています。 この関数では、このオブジェクトのデータは変更されません。 多くの場合、ステータスを設定する使用となり、`null`または**無効な**です。 注意してください、代入演算子 ([演算子 =](#eq)) と[SetDateTimeSpan](#setdatetimespan)ソース値に基づいて、オブジェクトの状態を設定しないでください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&22;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_13.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [時刻クラス](../../atl-mfc-shared/reference/coledatetime-class.md)   
 [CTime クラス](../../atl-mfc-shared/reference/ctime-class.md)   
 [CTimeSpan クラス](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL と MFC クラスの共有](../../atl-mfc-shared/atl-mfc-shared-classes.md)



