---
title: ATL 演算子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bcbe04fb057ffc8077f422cd784b5d31691df1e3
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/10/2018
---
# <a name="atl-operators"></a>ATL 演算子
このセクションには、ATL グローバル演算子のリファレンス トピックが含まれています。  
  
|演算子|説明|  
|--------------|-----------------|  
|[operator ==](#operator_eq_eq)|比較する 2 つ`CSid`オブジェクトまたは`SID`構造が等しいかどうか。|  
|[operator !=](#operator_neq)|比較する 2 つ`CSid`オブジェクトまたは`SID`非等値の構造体。|  
|[operator <](#operator_lt)|かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造体より小さい`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。|  
|[operator >](#operator_gt)|かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造体より大きい、`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。|  
|[operator <=](#operator_lt__eq)|かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造体は、以下に、`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。|  
|[operator >=](#operator_gt__eq)|かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造がより大きいか等しい、`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h です。  
  
##  <a name="operator_eq_eq"></a>  operator ==  
 比較`CSid`オブジェクトまたは`SID`等しいかどうか (セキュリティ識別子) 構造体。  
  
```   
bool operator==(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 最初の`CSid`オブジェクトまたは`SID`に比較します。  
  
 `rhs`  
 2 番目`CSid`オブジェクトまたは`SID`に比較します。  
  
### <a name="return-value"></a>戻り値  
 返します**true**オブジェクトが等しい場合は**false**両者が等しくない場合。  
  
##  <a name="operator_neq"></a>  operator !=  
 比較`CSid`オブジェクトまたは`SID`非等値の (セキュリティ識別子) 構造体。  
  
```   
bool operator==(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 最初の`CSid`オブジェクトまたは`SID`に比較します。  
  
 `rhs`  
 2 番目`CSid`オブジェクトまたは`SID`に比較します。  
  
### <a name="return-value"></a>戻り値  
 返します**true**オブジェクトが等しくない場合**false**が等しい場合は。  
  
##  <a name="operator_lt"></a>  operator <  
 かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造体より小さい`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 最初の`CSid`オブジェクトまたは`SID`に比較します。  
  
 `rhs`  
 2 番目`CSid`オブジェクトまたは`SID`に比較します。  
  
### <a name="return-value"></a>戻り値  
 返します**true**場合のアドレス、`lhs`オブジェクトがのアドレスより小さい、`rhs`オブジェクト、 **false**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 この演算子のアドレスに、`CSid`オブジェクトまたは`SID`構造、および C++ 標準ライブラリのコレクション クラスとの互換性を提供する実装します。  
  
##  <a name="operator_gt"></a>  operator >  
 かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造体より大きい、`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 最初の`CSid`オブジェクトまたは`SID`に比較します。  
  
 `rhs`  
 2 番目`CSid`オブジェクトまたは`SID`に比較します。  
  
### <a name="return-value"></a>戻り値  
 返します**true**場合のアドレス、`lhs`のアドレスより大きい、 `rhs`、 **false**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 この演算子のアドレスに、`CSid`オブジェクトまたは`SID`構造、および C++ 標準ライブラリのコレクション クラスとの互換性を提供する実装します。  
  
##  <a name="operator_lt__eq"></a>  operator <=  
 かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造体は、以下に、`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 最初の`CSid`オブジェクトまたは`SID`に比較します。  
  
 `rhs`  
 2 番目`CSid`オブジェクトまたは`SID`に比較します。  
  
### <a name="return-value"></a>戻り値  
 返します**true**場合のアドレス、`lhs`以下のアドレスには、 `rhs`、 **false**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 この演算子のアドレスに、`CSid`オブジェクトまたは`SID`構造、および C++ 標準ライブラリのコレクション クラスとの互換性を提供する実装します。  
  
##  <a name="operator_gt__eq"></a>  operator >=  
 かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造がより大きいか等しい、`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 最初の`CSid`オブジェクトまたは`SID`に比較します。  
  
 `rhs`  
 2 番目`CSid`オブジェクトまたは`SID`に比較します。  
  
### <a name="return-value"></a>戻り値  
 返します**true**場合のアドレス、`lhs`以上のアドレスには、 `rhs`、 **false**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 この演算子のアドレスに、`CSid`オブジェクトまたは`SID`構造、および C++ 標準ライブラリのコレクション クラスとの互換性を提供する実装します。



