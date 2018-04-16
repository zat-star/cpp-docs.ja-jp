---
title: "CAtlException クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlException
- ATLEXCEPT/ATL::CAtlException
- ATLEXCEPT/ATL::CAtlException::CAtlException
- ATLEXCEPT/ATL::CAtlException::m_hr
dev_langs:
- C++
helpviewer_keywords:
- CAtlException class
ms.assetid: 3fd7b041-f70d-4292-b947-0d70781d95a8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0af7fa5a0bc78043e0eac204255f30ab1b9672c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="catlexception-class"></a>CAtlException クラス
このクラスは、ATL の例外を定義します。  
  
## <a name="syntax"></a>構文  
  
```
class CAtlException
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlException::CAtlException](#catlexception)|コンストラクターです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlException::operator HRESULT](#operator_hresult)|HRESULT 値を現在のオブジェクトをキャストします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlException::m_hr](#m_hr)|型の変数 HRESULT は、オブジェクトによって作成され、エラー状態を格納するために使用します。|  
  
## <a name="remarks"></a>コメント  
 A`CAtlException`オブジェクト ATL 操作に関する例外条件を表します。 `CAtlException`クラスには、例外と HRESULT の場合と同様に、例外を処理できるようにするキャスト演算子の原因を示すステータス コードを格納するパブリック データ メンバーが含まれています。  
  
 一般が呼び出す`AtlThrow`を作成するのではなく、`CAtlException`オブジェクトに直接です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlexcept.h  
  
##  <a name="catlexception"></a>CAtlException::CAtlException  
 コンストラクターです。  
  
```
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hr`  
 `HRESULT`エラー コード。  
  
##  <a name="operator_hresult"></a>CAtlException::operator HRESULT 
 HRESULT 値を現在のオブジェクトをキャストします。  
  
```  
operator HRESULT() const throw ();
```  
  
##  <a name="m_hr"></a>CAtlException::m_hr  
 `HRESULT`データ メンバーです。  
  
```
HRESULT m_hr;
```  
  
### <a name="remarks"></a>コメント  
 エラー状態を格納するデータ メンバーです。 HRESULT 値は、コンス トラクターによって設定[CAtlException::CAtlException](#catlexception)です。  
  
## <a name="see-also"></a>参照  
 [AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)   
 [クラスの概要](../../atl/atl-class-overview.md)
