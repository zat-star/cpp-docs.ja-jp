---
title: "クラスの持つ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileTimeSpan
- ATL.CFileTimeSpan
- ATL::CFileTimeSpan
dev_langs:
- C++
helpviewer_keywords:
- shared classes, CFileTimeSpan
- CFileTimeSpan class
ms.assetid: 5856fb39-9c82-4027-8ccf-8760890491ec
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
ms.openlocfilehash: 8a25bab65d9e5705a71eddde901e747c43a5a002
ms.lasthandoff: 02/24/2017

---
# <a name="cfiletimespan-class"></a>持つクラス
このクラスは、相対的な日付と時刻の値がファイルへの関連付けを管理するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CFileTimeSpan
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFileTimeSpan::CFileTimeSpan](#cfiletimespan)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFileTimeSpan::GetTimeSpan](#gettimespan)|タイム スパンを取得するには、このメソッドを呼び出して、`CFileTimeSpan`オブジェクトです。|  
|[CFileTimeSpan::SetTimeSpan](#settimespan)|時間の範囲を設定するには、このメソッドを呼び出す、`CFileTimeSpan`オブジェクトです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CFileTimeSpan::operator-](#operator_-)|減算を実行、`CFileTimeSpan`オブジェクトです。|  
|[CFileTimeSpan::operator! =](#operator_neq)|2 つの `CFileTimeSpan` オブジェクトが等しくないかどうかを比較します。|  
|[CFileTimeSpan::operator +](#operator_add)|加算を実行する、`CFileTimeSpan`オブジェクトです。|  
|[CFileTimeSpan::operator + = 演算子](#operator_add_eq)|加算を実行する、`CFileTimeSpan`オブジェクトし、結果を現在のオブジェクトに代入します。|  
|[CFileTimeSpan::operator&lt;](#operator_lt)|2 つを比較して`CFileTimeSpan`小さい方を決定するオブジェクト。|  
|[CFileTimeSpan::operator&lt;=](#operator_lt_eq)|2 つを比較して`CFileTimeSpan`オブジェクトが等しいかどうか、または、小さい方を判断します。|  
|[CFileTimeSpan::operator =](#operator_eq)|代入演算子です。|  
|[CFileTimeSpan::operator =](#operator_-_eq)|減算を実行、`CFileTimeSpan`オブジェクトし、結果を現在のオブジェクトに代入します。|  
|[CFileTimeSpan::operator = =](#operator_eq_eq)|2 つの `CFileTimeSpan` オブジェクトが等しいかどうかを比較します。|  
|[CFileTimeSpan::operator&gt;](#operator_gt)|2 つを比較して`CFileTimeSpan`オブジェクトのうち、大きい方を決定します。|  
|[CFileTimeSpan::operator&gt;=](#operator_gt_eq)|2 つを比較して`CFileTimeSpan`オブジェクトが等しいかどうか、または、大きい方を判断します。|  
  
## <a name="remarks"></a>コメント  
 このクラスには相対的な期間を管理するためのメソッドの時に関する操作を実行するときに、一般的に、ファイルが作成、最後にアクセスまたは最後に変更されました。 このクラスのメソッドは頻繁と組み合わせて使用[加算クラス](../../atl-mfc-shared/reference/cfiletime-class.md)オブジェクトです。  
  
## <a name="example"></a>例  
 例を参照してください[CFileTime::Millisecond](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atltime.h  
  
##  <a name="a-namecfiletimespana--cfiletimespancfiletimespan"></a><a name="cfiletimespan"></a>CFileTimeSpan::CFileTimeSpan  
 コンストラクターです。  
  
```
CFileTimeSpan() throw();
CFileTimeSpan(const CFileTimeSpan& span) throw();
CFileTimeSpan(LONGLONG nSpan) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 既存の `CFileTimeSpan` オブジェクト。  
  
 `nSpan`  
 時間 (ミリ秒) の期間。  
  
### <a name="remarks"></a>コメント  
 `CFileTimeSpan`既存を使用してオブジェクトを作成できる`CFileTimeSpan`オブジェクト、または 64 ビット値として表されます。 既定のコンス トラクターは、時間間隔を 0 に設定します。  
  
##  <a name="a-namegettimespana--cfiletimespangettimespan"></a><a name="gettimespan"></a>CFileTimeSpan::GetTimeSpan  
 タイム スパンを取得するには、このメソッドを呼び出して、`CFileTimeSpan`オブジェクトです。  
  
```
LONGLONG GetTimeSpan() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 時間間隔をミリ秒単位で返します。  
  
##  <a name="a-nameoperator-a--cfiletimespanoperator--"></a><a name="operator_-"></a>CFileTimeSpan::operator-  
 減算を実行、**持つ**オブジェクトです。  
  
```
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します。、 `CFileTimeSpan`&2; つの期間の違いの結果を表すオブジェクト。  
  
##  <a name="a-nameoperatorneqa--cfiletimespanoperator-"></a><a name="operator_neq"></a>CFileTimeSpan::operator! =  
 2 つの `CFileTimeSpan` オブジェクトが等しくないかどうかを比較します。  
  
```
bool operator!=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 比較される `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**比較対象のアイテムがと等しくない場合、`CFileTimeSpan`オブジェクト。 それ以外の場合**false**します。  
  
##  <a name="a-nameoperatoradda--cfiletimespanoperator-"></a><a name="operator_add"></a>CFileTimeSpan::operator +  
 加算を実行する、`CFileTimeSpan`オブジェクトです。  
  
```
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します。、`CFileTimeSpan`にまたがる&2; つの時間の合計を含むオブジェクト。  
  
##  <a name="a-nameoperatoraddeqa--cfiletimespanoperator-"></a><a name="operator_add_eq"></a>CFileTimeSpan::operator + = 演算子  
 加算を実行する、`CFileTimeSpan`オブジェクトし、結果、現在のオブジェクトに代入します。  
  
```
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 取得、更新された`CFileTimeSpan`にまたがる&2; つの時間の合計を含むオブジェクトします。  
  
##  <a name="a-nameoperatorlta--cfiletimespanoperator-lt"></a><a name="operator_lt"></a>CFileTimeSpan::operator&lt;  
 2 つを比較して`CFileTimeSpan`小さい方を決定するオブジェクト。  
  
```
bool operator<(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 比較される `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**最初のオブジェクトが小さい場合 (つまり、より短い期間を表す)&2; 番目のそれ以外の場合**false**します。  
  
##  <a name="a-nameoperatorlteqa--cfiletimespanoperator-lt"></a><a name="operator_lt_eq"></a>CFileTimeSpan::operator&lt;=  
 2 つを比較して`CFileTimeSpan`オブジェクトが等しいかどうか、または、小さい方を判断します。  
  
```
bool operator<=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 比較される `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**最初のオブジェクトが (つまり、より短い期間を表す) よりも小さい場合、またはそれ以外の場合、秒に等しい**false**します。  
  
##  <a name="a-nameoperatoreqa--cfiletimespanoperator-"></a><a name="operator_eq"></a>CFileTimeSpan::operator =  
 代入演算子です。  
  
```
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 取得、更新された`CFileTimeSpan`オブジェクトです。  
  
##  <a name="a-nameoperator-eqa--cfiletimespanoperator--"></a><a name="operator_-_eq"></a>CFileTimeSpan::operator =  
 減算を実行、`CFileTimeSpan`オブジェクトし、結果、現在のオブジェクトに代入します。  
  
```
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 取得、更新された`CFileTimeSpan`オブジェクトです。  
  
##  <a name="a-nameoperatoreqeqa--cfiletimespanoperator-"></a><a name="operator_eq_eq"></a>CFileTimeSpan::operator = =  
 2 つの `CFileTimeSpan` オブジェクトが等しいかどうかを比較します。  
  
```
bool operator==(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 比較される `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true** 、オブジェクトが等しい場合、それ以外の場合**false**します。  
  
##  <a name="a-nameoperatorgta--cfiletimespanoperator-gt"></a><a name="operator_gt"></a>CFileTimeSpan::operator&gt;  
 2 つを比較して`CFileTimeSpan`オブジェクトのうち、大きい方を決定します。  
  
```
bool operator>(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 比較される `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**最初のオブジェクトがより大きい場合 (つまり、より長い期間を表します)、2 番目よりもそれ以外の場合**false**します。  
  
##  <a name="a-nameoperatorgteqa--cfiletimespanoperator-gt"></a><a name="operator_gt_eq"></a>CFileTimeSpan::operator&gt;=  
 2 つを比較して`CFileTimeSpan`オブジェクトが等しいかどうか、または、大きい方を判断します。  
  
```
bool operator>=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 比較される `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**最初のオブジェクトがより大きい場合 (つまり、より長い期間を表します)、またはそれ以外の場合、秒に等しい**false**します。  
  
##  <a name="a-namesettimespana--cfiletimespansettimespan"></a><a name="settimespan"></a>CFileTimeSpan::SetTimeSpan  
 時間の範囲を設定するには、このメソッドを呼び出す、`CFileTimeSpan`オブジェクトです。  
  
```
void SetTimeSpan(LONGLONG nSpan) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nSpan`  
 ミリ秒単位の時間の長さの新しい値。  
  
## <a name="see-also"></a>関連項目  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [加算クラス](../../atl-mfc-shared/reference/cfiletime-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL と MFC クラスの共有](../../atl-mfc-shared/atl-mfc-shared-classes.md)



