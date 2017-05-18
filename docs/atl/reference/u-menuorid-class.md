---
title: "_U_MENUorID クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL._U_MENUorID
- ATL::_U_MENUorID
- _U_MENUorID
dev_langs:
- C++
helpviewer_keywords:
- U_MENUorID class
- _U_MENUorID class
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: f7c0a5c34c4e103f830a029f58cdfa00dcb58a32
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="umenuorid-class"></a>_U_MENUorID クラス
このクラスのラッパーを提供する**CreateWindow**と**CreateWindowEx**します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class _U_MENUorID
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[_U_MENUorID::_U_MENUorID](#_u_menuorid___u_menuorid)|コンストラクターです。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[_U_MENUorID::m_hMenu](#_u_menuorid__m_hmenu)|メニューへのハンドル。|  
  
## <a name="remarks"></a>コメント  
 この引数アダプター クラスにより、いずれかの Id ( **UINT**s) またはメニュー ハンドル ( `HMENU`s)、呼び出し元の一部で明示的なキャストを必要とせず、関数に渡されます。  
  
 このクラスは、Windows API のラッパーを実装するために設計されていますが、特に[CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)と[CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)関数、どちらもそのまま使用、`HMENU`子ウィンドウの識別子の可能性がある引数 ( **UINT**) メニュー ハンドルではなく。 たとえば、このクラスの使用を表示へのパラメーターとして[CWindowImpl::Create](cwindowimpl-class.md#create)します。  

  
 クラスは&2; つのコンス トラクター オーバー ロードを定義します。&1; つを受け入れる、 **UINT**引数であり、もう一方を受け入れる、`HMENU`引数。 **UINT**引数にキャスト、 `HMENU` 、コンス トラクターやクラスの&1; つのデータ メンバーに保存された結果で[m_hMenu](#_u_menuorid__m_hmenu)します。 引数、`HMENU`コンス トラクターは、変換せずに直接格納します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="_u_menuorid__m_hmenu"></a>_U_MENUorID::m_hMenu  
 クラスでは、パブリック コンス トラクターのいずれかに渡された値`HMENU`データ メンバーです。  
  
```
HMENU m_hMenu;
```  
  
##  <a name="_u_menuorid___u_menuorid"></a>_U_MENUorID::_U_MENUorID  
 **UINT**引数にキャスト、 `HMENU` 、コンス トラクターやクラスの&1; つのデータ メンバーに保存された結果で[m_hMenu](#_u_menuorid__m_hmenu)します。  
  
```
_U_MENUorID(UINT nID);  
_U_MENUorID(HMENU hMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 子ウィンドウの識別子です。  
  
 `hMenu`  
 メニューのハンドル。  
  
### <a name="remarks"></a>コメント  
 引数、`HMENU`コンス トラクターは、変換せずに直接格納します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

