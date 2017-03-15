---
title: "CComSafeArrayBound クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComSafeArrayBound
- ATL::CComSafeArrayBound
- CComSafeArrayBound
dev_langs:
- C++
helpviewer_keywords:
- CComSafeArrayBound class
ms.assetid: dd6299db-5f84-4630-bbf0-f5add5318437
caps.latest.revision: 21
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 1cc2adef85c902b7ad12b152b35a7ef68e6abacb
ms.lasthandoff: 02/24/2017

---
# <a name="ccomsafearraybound-class"></a>CComSafeArrayBound クラス
このクラスは、用のラッパー、 [SAFEARRAYBOUND](http://msdn.microsoft.com/en-us/303a9bdb-71d6-4f14-8747-84cf84936c6d)構造体。  
  
## <a name="syntax"></a>構文  
  
```
class CComSafeArrayBound : public SAFEARRAYBOUND
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CComSafeArrayBound](#ccomsafearraybound)|コンストラクターです。|  
|[GetCount](#getcount)|このメソッドでは、要素の数を取得します。|  
|[GetLowerBound](#getlowerbound)|下限の境界を返すには、このメソッドを呼び出します。|  
|[です](#getupperbound)|上限の境界を返すには、このメソッドを呼び出します。|  
|[SetCount](#setcount)|要素の数を設定するには、このメソッドを呼び出します。|  
|[SetLowerBound](#setlowerbound)|下限の境界を設定するには、このメソッドを呼び出します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 =](#operator_eq)|セット、`CComSafeArrayBound`を新しい値にします。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、用のラッパー、 **SAFEARRAYBOUND**によって使用される構造[CComSafeArray](../../atl/reference/ccomsafearray-class.md)します。 メソッドを提供してクエリを実行して、1 つのディメンションの上限と下限の境界を設定、`CComSafeArray`オブジェクトと含まれる要素の数。 多次元`CComSafeArray`オブジェクトの配列を使用して`CComSafeArrayBound`オブジェクト、ディメンションごとに&1; つです。 そのため、メソッドを使って[GetCount](#getcount)、このメソッドは多次元配列の要素の合計数事項を返すことはありません。  
  
 **ヘッダー:** atlsafe.h  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsafe.h  
  
##  <a name="a-nameccomsafearraybounda--ccomsafearrayboundccomsafearraybound"></a><a name="ccomsafearraybound"></a>CComSafeArrayBound::CComSafeArrayBound  
 コンストラクターです。  
  
```
CComSafeArrayBound(ULONG ulCount = 0, LONG lLowerBound = 0) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `ulCount`  
 配列の要素数。  
  
 `lLowerBound`  
 配列の番号を下限値です。  
  
### <a name="remarks"></a>コメント  
 配列が、Visual C プログラムからアクセスする場合は、下限を 0 として定義することをお勧めします。 配列の Visual Basic など他の言語で使用する場合は、別の下限値を使用するよりも望ましい場合があります。  
  
##  <a name="a-namegetcounta--ccomsafearrayboundgetcount"></a><a name="getcount"></a>CComSafeArrayBound::GetCount  
 このメソッドでは、要素の数を取得します。  
  
```
ULONG GetCount() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 要素の数を返します。  
  
### <a name="remarks"></a>コメント  
 場合、関連付けられている`CComSafeArray`オブジェクトは、多次元配列を表す、このメソッドは右端の次元で要素の合計数を返すのみです。 使用[CComSafeArray::GetCount](../../atl/reference/ccomsafearray-class.md#getcount)要素の合計数を取得します。  
  
##  <a name="a-namegetlowerbounda--ccomsafearrayboundgetlowerbound"></a><a name="getlowerbound"></a>CComSafeArrayBound::GetLowerBound  
 下限の境界を返すには、このメソッドを呼び出します。  
  
```
LONG GetLowerBound() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 下限値を返す、`CComSafeArrayBound`オブジェクトです。  
  
##  <a name="a-namegetupperbounda--ccomsafearrayboundgetupperbound"></a><a name="getupperbound"></a>CComSafeArrayBound::GetUpperBound  
 上限の境界を返すには、このメソッドを呼び出します。  
  
```
LONG GetUpperBound() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 上限値を返す、`CComSafeArrayBound`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 上限の境界は、要素および下限の境界値の数によって異なります。 たとえば、下限が 0 で、要素の数が 10 の場合上限の境界が 9 を自動的に設定されます。  
  
##  <a name="a-nameoperatoreqa--ccomsafearrayboundoperator-"></a><a name="operator_eq"></a>CComSafeArrayBound::operator =  
 セット、`CComSafeArrayBound`を新しい値にします。  
  
```
CComSafeArrayBound& operator= (const CComSafeArrayBound& bound) throw();
CComSafeArrayBound& operator= (ULONG ulCount) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `bound`  
 `CComSafeArrayBound` オブジェクト。  
  
 `ulCount`  
 要素の数。  
  
### <a name="return-value"></a>戻り値  
 ポインターを返す、`CComSafeArrayBound`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 `CComSafeArrayBound`オブジェクトは、既存を使用して割り当てることができます`CComSafeArrayBound`、またはケース下限の境界が設定されるを 0 に既定では、要素の数を指定しています。  
  
##  <a name="a-namesetcounta--ccomsafearrayboundsetcount"></a><a name="setcount"></a>CComSafeArrayBound::SetCount  
 要素の数を設定するには、このメソッドを呼び出します。  
  
```
ULONG SetCount(ULONG ulCount) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `ulCount`  
 要素の数。  
  
### <a name="return-value"></a>戻り値  
 要素の数を返す、`CComSafeArrayBound`オブジェクトです。  
  
##  <a name="a-namesetlowerbounda--ccomsafearrayboundsetlowerbound"></a><a name="setlowerbound"></a>CComSafeArrayBound::SetLowerBound  
 下限の境界を設定するには、このメソッドを呼び出します。  
  
```
LONG SetLowerBound(LONG lLowerBound) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lLowerBound`  
 下限値です。  
  
### <a name="return-value"></a>戻り値  
 新しい下限値を返す、`CComSafeArrayBound`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 配列が、Visual C プログラムからアクセスする場合は、下限を 0 として定義することをお勧めします。 配列の Visual Basic など他の言語で使用する場合は、別の下限値を使用するよりも望ましい場合があります。  
  
 上限の境界は、要素および下限の境界値の数によって異なります。 たとえば、下限が 0 で、要素の数が 10 の場合上限の境界が 9 を自動的に設定されます。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

