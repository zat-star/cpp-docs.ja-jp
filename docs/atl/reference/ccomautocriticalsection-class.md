---
title: "CComAutoCriticalSection クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 9f58a4cfd02af09a05b625a7e02b574b672adade
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ccomautocriticalsection-class"></a>CComAutoCriticalSection クラス
`CComAutoCriticalSection`取得し、クリティカル セクション オブジェクトの所有権を解放するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CComAutoCriticalSection : public CComCriticalSection
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComAutoCriticalSection::CComAutoCriticalSection](#ccomautocriticalsection)|コンストラクターです。|  
|[CComAutoCriticalSection:: ~ CComAutoCriticalSection](#dtor)|デストラクターです。|  
  
## <a name="remarks"></a>コメント  
 `CComAutoCriticalSection`クラスのような[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)、以外`CComAutoCriticalSection`コンス トラクターでクリティカル セクション オブジェクトを自動的に初期化します。  
  
 通常、使用して`CComAutoCriticalSection`を通じて、`typedef`名[AutoCriticalSection](ccommultithreadmodel-class.md#autocriticalsection)します。 この名前を参照して`CComAutoCriticalSection`と[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)が使用されています。  

  
 `Init`と`Term`からメソッド[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)このクラスを使用する場合は使用できません。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComAutoCriticalSection`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcore.h  
  
##  <a name="ccomautocriticalsection"></a>CComAutoCriticalSection::CComAutoCriticalSection  
 コンストラクターです。  
  
```
CComAutoCriticalSection();
```  
  
### <a name="remarks"></a>コメント  
 Win32 関数を呼び出す[InitializeCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms683472)、クリティカル セクション オブジェクトを初期化します。  
  
##  <a name="dtor"></a>CComAutoCriticalSection:: ~ CComAutoCriticalSection  
 デストラクターです。  
  
```
~CComAutoCriticalSection() throw();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターの呼び出し[DeleteCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682552)、クリティカル セクション オブジェクトによって使用されているすべてのシステム リソースを解放します。  
  
## <a name="see-also"></a>関連項目  
 [CComFakeCriticalSection クラス](../../atl/reference/ccomfakecriticalsection-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CComCriticalSection クラス](../../atl/reference/ccomcriticalsection-class.md)

