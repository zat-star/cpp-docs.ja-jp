---
title: "CAtlException クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlException
- ATL::CAtlException
- ATL.CAtlException
dev_langs:
- C++
helpviewer_keywords:
- CAtlException class
ms.assetid: 3fd7b041-f70d-4292-b947-0d70781d95a8
caps.latest.revision: 19
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
ms.openlocfilehash: 30c9235f16581c86ab5612522909dc366b1ce17e
ms.lasthandoff: 02/24/2017

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
|[CAtlException::operator HRESULT](#operator_hresult)|HRESULT 値を現在のオブジェクトにキャストします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlException::m_hr](#m_hr)|型の変数 HRESULT は、オブジェクトによって作成され、エラー状態を格納するために使用します。|  
  
## <a name="remarks"></a>コメント  
 A`CAtlException`オブジェクト ATL 操作に関する例外条件を表します。 `CAtlException`クラスには、例外と HRESULT の場合と同様に、例外を処理できるようにするキャスト演算子の理由を示すステータス コードを格納するパブリック データ メンバーが含まれています。  
  
 一般を呼び出す`AtlThrow`を作成するのではなく、`CAtlException`オブジェクトに直接します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlexcept.h  
  
##  <a name="a-namecatlexceptiona--catlexceptioncatlexception"></a><a name="catlexception"></a>CAtlException::CAtlException  
 コンストラクターです。  
  
```
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hr`  
 `HRESULT`エラー コード。  
  
##  <a name="a-nameoperatorhresulta--catlexceptionoperator-hresult"></a><a name="operator_hresult"></a>CAtlException::operator HRESULT 
 HRESULT 値を現在のオブジェクトにキャストします。  
  
```  
operator HRESULT() const throw ();
```  
  
##  <a name="a-namemhra--catlexceptionmhr"></a><a name="m_hr"></a>CAtlException::m_hr  
 `HRESULT`データ メンバーです。  
  
```
HRESULT m_hr;
```  
  
### <a name="remarks"></a>コメント  
 エラー状態を格納するデータ メンバー。 HRESULT 値は、コンス トラクターによって設定[CAtlException::CAtlException](#catlexception)します。  
  
## <a name="see-also"></a>関連項目  
 [ため](http://msdn.microsoft.com/library/2bd111da-8170-488d-914a-c9bf6b6765f7)   
 [クラスの概要](../../atl/atl-class-overview.md)

