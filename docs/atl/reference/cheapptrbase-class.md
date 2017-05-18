---
title: "CHeapPtrBase クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase::AllocateBytes
- ATLCORE/ATL::CHeapPtrBase::Attach
- ATLCORE/ATL::CHeapPtrBase::Detach
- ATLCORE/ATL::CHeapPtrBase::Free
- ATLCORE/ATL::CHeapPtrBase::ReallocateBytes
- ATLCORE/ATL::CHeapPtrBase::m_pData
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtrBase class
ms.assetid: 501ac1b2-fb34-4c72-b7e6-a4f1fc8fda21
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 8084104489f6f1e2358ce0cbb573f4e20a0c4fce
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cheapptrbase-class"></a>CHeapPtrBase クラス
このクラスは、いくつかのヒープのスマート ポインター クラスの基礎を形成します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T, class Allocator = CCRTAllocator>  
class CHeapPtrBase
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 ヒープに格納されるオブジェクトの型。  
  
 `Allocator`  
 メモリの割り当ては、使用するクラス。 既定では、CRT ルーチンは、メモリ割り当てし、解放に使用されます。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CHeapPtrBase:: ~ CHeapPtrBase](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CHeapPtrBase::AllocateBytes](#allocatebytes)|メモリを割り当てるには、このメソッドを呼び出します。|  
|[CHeapPtrBase::Attach](#attach)|既存のポインターの所有権を取得するには、このメソッドを呼び出します。|  
|[CHeapPtrBase::Detach](#detach)|ポインターの所有権を解放するには、このメソッドを呼び出します。|  
|[CHeapPtrBase::Free](#free)|指すオブジェクトを削除するには、このメソッドを呼び出して、`CHeapPtrBase`です。|  
|[CHeapPtrBase::ReallocateBytes](#reallocatebytes)|メモリを再割り当てするには、このメソッドを呼び出します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CHeapPtrBase::operator T *](#operator_t_star)|キャスト演算子です。|  
|[CHeapPtrBase::operator >/documents/report1.rdl」の](#operator_amp)|&Gt;/documents/report1.rdl」の演算子です。|  
|[-> CHeapPtrBase::operator](#operator_ptr)|メンバーへのポインター演算子です。|  

  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CHeapPtrBase::m_pData](#m_pdata)|ポインターのデータ メンバー変数です。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、いくつかのヒープのスマート ポインター クラスの基礎を形成します。 派生クラス[CHeapPtr](../../atl/reference/cheapptr-class.md)と[CComHeapPtr](../../atl/reference/ccomheapptr-class.md)、コンス トラクターと演算子を追加します。 これらのクラスの実装例を参照してください。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcore.h  
  
##  <a name="allocatebytes"></a>CHeapPtrBase::AllocateBytes  
 メモリを割り当てるには、このメソッドを呼び出します。  
  
```
bool AllocateBytes(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nBytes`  
 割り当てるメモリのバイト数。  
  
### <a name="return-value"></a>戻り値  
 メモリが正常にある場合は true、割り当て false それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドで、アサーション エラーが発生場合、 [CHeapPtrBase::m_pData](#m_pdata)メンバー変数は、現在は、既存の値を指します。 つまり、null はありません。  
  
##  <a name="attach"></a>CHeapPtrBase::Attach  
 既存のポインターの所有権を取得するには、このメソッドを呼び出します。  
  
```
void Attach(T* pData) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pData`  
 `CHeapPtrBase` This ポインターの所有権を持つオブジェクト。  
  
### <a name="remarks"></a>コメント  
 ときに、`CHeapPtrBase`オブジェクトへのポインターの所有権を取得するに自動的に削除されますポインターと、割り当てられているデータ スコープ外になったときにします。  
  
 デバッグ ビルドで、アサーション エラーが発生場合、 [CHeapPtrBase::m_pData](#m_pdata)メンバー変数は、現在は、既存の値を指します。 つまり、null はありません。  
  
##  <a name="dtor"></a>CHeapPtrBase:: ~ CHeapPtrBase  
 デストラクターです。  
  
```
~CHeapPtrBase() throw();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放します。  
  
##  <a name="detach"></a>CHeapPtrBase::Detach  
 ポインターの所有権を解放するには、このメソッドを呼び出します。  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ポインターのコピーを返します。  
  
### <a name="remarks"></a>コメント  
 ポインターの所有権を解放、 [CHeapPtrBase::m_pData](#m_pdata)メンバー変数を NULL にし、ポインターのコピーを返します。  
  
##  <a name="free"></a>CHeapPtrBase::Free  
 指すオブジェクトを削除するには、このメソッドを呼び出して、`CHeapPtrBase`です。  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>コメント  
 によって指されるオブジェクト、`CHeapPtrBase`が解放されると、 [CHeapPtrBase::m_pData](#m_pdata)メンバー変数が NULL に設定します。  
  
##  <a name="m_pdata"></a>CHeapPtrBase::m_pData  
 ポインターのデータ メンバー変数です。  
  
```
T* m_pData;
```  
  
### <a name="remarks"></a>コメント  
 このメンバー変数は、ポインターの情報を保持します。  
  
##  <a name="operator_amp"></a>CHeapPtrBase::operator&amp;  
 &Gt;/documents/report1.rdl」の演算子です。  
  
```
T** operator&() throw();
```  
  
### <a name="return-value"></a>戻り値  
 によって指されるオブジェクトのアドレスを返す、`CHeapPtrBase`オブジェクトです。  
  

##  <a name="operator_ptr"></a>CHeapPtrBase::operator-&gt;  

 メンバーへのポインター演算子です。  
  
```
T* operator->() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 値を返す、 [CHeapPtrBase::m_pData](#m_pdata)メンバー変数です。  
  
### <a name="remarks"></a>コメント  
 この演算子が指すクラスのメソッドを呼び出すを使用して、`CHeapPtrBase`オブジェクトです。 デバッグ ビルドで、アサーション エラーが発生場合、`CHeapPtrBase`が NULL を指します。  
  
##  <a name="operator_t_star"></a>CHeapPtrBase::operator T *  
 キャスト演算子です。  
  
```  
operator T*() const throw();
```  
  
### <a name="remarks"></a>コメント  
 返します。 [CHeapPtrBase::m_pData](#m_pdata)します。  
  
##  <a name="reallocatebytes"></a>CHeapPtrBase::ReallocateBytes  
 メモリを再割り当てするには、このメソッドを呼び出します。  
  
```
bool ReallocateBytes(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nBytes`  
 新しいメモリの量 (バイト単位) を割り当てるに。  
  
### <a name="return-value"></a>戻り値  
 メモリが正常にある場合は true、割り当て false それ以外の場合。  
  
## <a name="see-also"></a>関連項目  
 [CHeapPtr クラス](../../atl/reference/cheapptr-class.md)   
 [CComHeapPtr クラス](../../atl/reference/ccomheapptr-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

