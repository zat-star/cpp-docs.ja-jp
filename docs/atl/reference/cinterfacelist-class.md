---
title: "CInterfaceList クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInterfaceList
- ATLCOLL/ATL::CInterfaceList
- ATLCOLL/ATL::CInterfaceList::CInterfaceList
dev_langs:
- C++
helpviewer_keywords:
- CInterfaceList class
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 50d86163080c5a0d0a7bb9ed6d77a40ac73722e7
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cinterfacelist-class"></a>CInterfaceList クラス
このクラスは、COM インターフェイス ポインターのリストを構築するときに役立つメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
template<class I, const IID* piid =& __uuidof(I)>  
class CInterfaceList 
   : public CAtlList<ATL::CComQIPtr<I, piid>,
                     CComQIPtrElementTraits<I, piid>>
```  
  
#### <a name="parameters"></a>パラメーター  
 `I`  
 格納されるポインターの型を指定する COM インターフェイスです。  
  
 `piid`  
 IID へのポインター`I`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CInterfaceList::CInterfaceList](#cinterfacelist)|インターフェイスの一覧のコンス トラクターです。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、コンス トラクターおよび COM インターフェイス ポインターのリストを作成するための派生メソッドを提供します。 使用[CInterfaceArray](../../atl/reference/cinterfacearray-class.md)配列が必要な場合です。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CInterfaceList`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="cinterfacelist"></a>CInterfaceList::CInterfaceList  
 インターフェイスの一覧のコンス トラクターです。  
  
```
CInterfaceList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nBlockSize`  
 ブロック サイズを既定値は 10 です。  
  
### <a name="remarks"></a>コメント  
 ブロック サイズは、新しい要素が必要なときに割り当てられたメモリの量の測定値です。 ブロック サイズの増加はメモリ割り当てルーチンの呼び出しを減らすためより多くのリソースを使用します。  
  
## <a name="see-also"></a>関連項目  
 [CAtlList クラス](../../atl/reference/catllist-class.md)   
 [CComQIPtr クラス](../../atl/reference/ccomqiptr-class.md)   
 [CComQIPtrElementTraits クラス](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

