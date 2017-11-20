---
title: "CInterfaceList クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInterfaceList
- ATLCOLL/ATL::CInterfaceList
- ATLCOLL/ATL::CInterfaceList::CInterfaceList
dev_langs: C++
helpviewer_keywords: CInterfaceList class
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 86e92f86896ac7c5a06b73a68e2d6889d10ea87b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
 格納するポインターの種類を指定する COM インターフェイスです。  
  
 `piid`  
 IID へのポインター`I`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CInterfaceList::CInterfaceList](#cinterfacelist)|インターフェイス リストのコンス トラクターです。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、コンス トラクターおよび COM インターフェイス ポインターのリストを作成するための派生メソッドを提供します。 使用して[CInterfaceArray](../../atl/reference/cinterfacearray-class.md)配列が必要な場合です。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CInterfaceList`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="cinterfacelist"></a>CInterfaceList::CInterfaceList  
 インターフェイス リストのコンス トラクターです。  
  
```
CInterfaceList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nBlockSize`  
 ブロック サイズを既定値は 10 です。  
  
### <a name="remarks"></a>コメント  
 ブロック サイズは、新しい要素が必要な場合に割り当てられたメモリの量の測定です。 ブロック サイズを大きくはメモリ割り当てルーチンに呼び出しを減らすことより多くのリソースを使用します。  
  
## <a name="see-also"></a>関連項目  
 [CAtlList クラス](../../atl/reference/catllist-class.md)   
 [CComQIPtr クラス](../../atl/reference/ccomqiptr-class.md)   
 [CComQIPtrElementTraits クラス](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
