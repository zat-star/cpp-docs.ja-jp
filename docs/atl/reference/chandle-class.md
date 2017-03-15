---
title: "CHandle クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CHandle
- ATL::CHandle
- CHandle
dev_langs:
- C++
helpviewer_keywords:
- CHandle class
ms.assetid: 883e9db5-40ec-4e29-9c74-4dd2ddd2e35d
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
ms.openlocfilehash: bbc0703ae5eaab01c0819be7e378509c7dc579ef
ms.lasthandoff: 02/24/2017

---
# <a name="chandle-class"></a>CHandle クラス
このクラスは、作成してオブジェクトのハンドルを使用するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CHandle
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CHandle::CHandle](#chandle)|コンストラクターです。|  
|[CHandle:: ~ CHandle](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CHandle::Attach](#attach)|アタッチするには、このメソッドを呼び出して、`CHandle`オブジェクトを既存のハンドル。|  
|[CHandle::Close](#close)|終了するには、このメソッドを呼び出して、`CHandle`オブジェクトです。|  
|[CHandle::Detach](#detach)|ハンドルをデタッチするには、このメソッドを呼び出して、`CHandle`オブジェクトです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CHandle::operator ハンドル](#operator_handle)|格納されたハンドルの値を返します。|  
|[CHandle::operator =](#operator_eq)|代入演算子。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CHandle::m_h](#m_h)|ハンドルを格納するメンバー変数です。|  
  
## <a name="remarks"></a>コメント  
 A`CHandle`ハンドルが必要な場合に、オブジェクトを使用できます。 その主な違いは、`CHandle`オブジェクトは自動的に削除されます。  
  
> [!NOTE]
>  一部の API 関数は、INVALID_HANDLE_VALUE を使用して他のユーザーに、空または無効なハンドルとして NULL を使用します。 `CHandle`NULL ではだけが使用では、実際のハンドルとして INVALID_HANDLE_VALUE を扱います。 INVALID_HANDLE_VALUE を返すことができる API を呼び出す場合は、呼び出す前にこの値の確認する必要があります[CHandle::Attach](#attach)に渡すか、`CHandle`コンス トラクターを代わりに NULL を渡します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="a-nameattacha--chandleattach"></a><a name="attach"></a>CHandle::Attach  
 アタッチするには、このメソッドを呼び出して、`CHandle`オブジェクトを既存のハンドル。  
  
```
void Attach(HANDLE h) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `h`  
 `CHandle`ハンドルの所有権を`h`します。  
  
### <a name="remarks"></a>コメント  
 代入、`CHandle`オブジェクトを`h`を処理します。 デバッグ ビルドは atlassert 場合`h`は NULL です。 ハンドルの妥当性に関するその他のチェックは行われません。  
  
##  <a name="a-namechandlea--chandlechandle"></a><a name="chandle"></a>CHandle::CHandle  
 コンストラクターです。  
  
```
CHandle() throw();
CHandle(CHandle& h) throw();
explicit CHandle(HANDLE h) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `h`  
 既存のハンドルまたは`CHandle`です。  
  
### <a name="remarks"></a>コメント  
 新たに作成`CHandle`オブジェクト、必要に応じて 既存のハンドルを使用して、または`CHandle`オブジェクトです。  
  
##  <a name="a-namedtora--chandlechandle"></a><a name="dtor"></a>CHandle:: ~ CHandle  
 デストラクターです。  
  
```
~CHandle() throw();
```  
  
### <a name="remarks"></a>コメント  
 解放、`CHandle`を呼び出してオブジェクト[CHandle::Close](#close)します。  
  
##  <a name="a-nameclosea--chandleclose"></a><a name="close"></a>CHandle::Close  
 終了するには、このメソッドを呼び出して、`CHandle`オブジェクトです。  
  
```
void Close() throw();
```  
  
### <a name="remarks"></a>コメント  
 開いているオブジェクト ハンドルを閉じます。 ハンドルがある場合に、ケース NULL の場合**閉じる**が既に呼び出されると、ATLASSERT がデバッグ ビルドで発生します。  
  
##  <a name="a-namedetacha--chandledetach"></a><a name="detach"></a>CHandle::Detach  
 ハンドルをデタッチするには、このメソッドを呼び出して、`CHandle`オブジェクトです。  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチされているハンドルを返します。  
  
### <a name="remarks"></a>コメント  
 ハンドルの所有権を解放します。  
  
##  <a name="a-namemha--chandlemh"></a><a name="m_h"></a>CHandle::m_h  
 ハンドルを格納するメンバー変数です。  
  
```
HANDLE m_h;
```  
  
##  <a name="a-nameoperatoreqa--chandleoperator-"></a><a name="operator_eq"></a>CHandle::operator =  
 代入演算子です。  
  
```
CHandle& operator=(CHandle& h) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `h`  
 `CHandle`ハンドルの所有権を`h`します。  
  
### <a name="return-value"></a>戻り値  
 新しいへの参照を返す`CHandle`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 場合、`CHandle`オブジェクトが現在のハンドルを含む、閉じられます。 `CHandle`オブジェクトに渡されるが、そのハンドルの参照を NULL に設定します。 これにより、2 つ`CHandle`オブジェクトは、同じアクティブなハンドルを格納できません。  
  
##  <a name="a-nameoperatorhandlea--chandleoperator-handle"></a><a name="operator_handle"></a>CHandle::operator ハンドル  
 格納されたハンドルの値を返します。  
  
```  
operator HANDLE() const throw();
```  
  
### <a name="remarks"></a>コメント  
 格納されている値を返す[CHandle::m_h](#m_h)します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

