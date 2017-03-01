---
title: "ATL 演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs:
- C++
helpviewer_keywords:
- operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
caps.latest.revision: 16
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
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 87aadf7aacc31ded165a8e1380823cb20e614fb1
ms.lasthandoff: 02/24/2017

---
# <a name="atl-operators"></a>ATL 演算子
このセクションには、ATL グローバル演算子のリファレンス トピックが含まれています。  
  
|演算子|説明|  
|--------------|-----------------|  
|[演算子 = =](#operator_eq_eq)|2 つを比較して`CSid`オブジェクトまたは`SID`構造体が等しいかどうか。|  
|[operator! =](#operator_neq)|2 つを比較して`CSid`オブジェクトまたは`SID`の非等値構造体。|  
|[演算子](#operator_lt)|かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造体より小さい`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。|  
|[演算子 >](#operator_gt)|かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造体がより大きい、`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。|  
|[演算子<>](#operator_lt__eq)|かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造体は、以下に、`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。|  
|[演算子 > =](#operator_gt__eq)|かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造がより大きいか等しい、`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。|  
  
 これらの演算子はすべてファイル atlsecurity.h で定義します。  
  
##  <a name="a-nameoperatoreqeqa--operator-"></a><a name="operator_eq_eq"></a>演算子 = =  
 比較`CSid`オブジェクトまたは`SID`(セキュリティ識別子) 構造体が等しいかどうか。  
  
```   
bool operator==(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 最初の`CSid`オブジェクトまたは`SID`比較する構造体。  
  
 `rhs`  
 2 番目`CSid`オブジェクトまたは`SID`比較する構造体。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**場合は、オブジェクトが等しく、 **false**両者が等しくない場合。  
  
##  <a name="a-nameoperatorneqa--operator-"></a><a name="operator_neq"></a>operator! =  
 比較`CSid`オブジェクトまたは`SID`の非等値 (セキュリティ識別子) 構造体。  
  
```   
bool operator==(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 最初の`CSid`オブジェクトまたは`SID`比較する構造体。  
  
 `rhs`  
 2 番目`CSid`オブジェクトまたは`SID`比較する構造体。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**オブジェクトが等しくない場合**false**が等しい場合は。  
  
##  <a name="a-nameoperatorlta--operator-"></a><a name="operator_lt"></a>演算子  
 かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造体より小さい`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 最初の`CSid`オブジェクトまたは`SID`比較する構造体。  
  
 `rhs`  
 2 番目`CSid`オブジェクトまたは`SID`比較する構造体。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**場合のアドレス、`lhs`オブジェクトがのアドレスより小さい、`rhs`オブジェクト、 **false**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 この演算子のアドレスに対して、`CSid`オブジェクトまたは`SID`構造、および C++ 標準ライブラリ コレクション クラスとの互換性を提供する実装します。  
  
##  <a name="a-nameoperatorgta--operator-"></a><a name="operator_gt"></a>演算子 >  
 かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造体がより大きい、`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 最初の`CSid`オブジェクトまたは`SID`比較する構造体。  
  
 `rhs`  
 2 番目`CSid`オブジェクトまたは`SID`比較する構造体。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**場合のアドレス、`lhs`のアドレスよりも大きい、 `rhs`、 **false**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 この演算子のアドレスに対して、`CSid`オブジェクトまたは`SID`構造、および C++ 標準ライブラリ コレクション クラスとの互換性を提供する実装します。  
  
##  <a name="a-nameoperatorlteqa--operator-"></a><a name="operator_lt__eq"></a>演算子<=></=>  
 かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造体は、以下に、`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 最初の`CSid`オブジェクトまたは`SID`比較する構造体。  
  
 `rhs`  
 2 番目`CSid`オブジェクトまたは`SID`比較する構造体。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**場合のアドレス、`lhs`は以下のアドレス、 `rhs`、 **false**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 この演算子のアドレスに対して、`CSid`オブジェクトまたは`SID`構造、および C++ 標準ライブラリ コレクション クラスとの互換性を提供する実装します。  
  
##  <a name="a-nameoperatorgteqa--operator-"></a><a name="operator_gt__eq"></a>演算子 > =  
 かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造がより大きいか等しい、`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 最初の`CSid`オブジェクトまたは`SID`比較する構造体。  
  
 `rhs`  
 2 番目`CSid`オブジェクトまたは`SID`比較する構造体。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**場合のアドレス、`lhs`以上のアドレスには、 `rhs`、 **false**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 この演算子のアドレスに対して、`CSid`オブジェクトまたは`SID`構造、および C++ 標準ライブラリ コレクション クラスとの互換性を提供する実装します。




