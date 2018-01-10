---
title: "_U_MENUorID クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL._U_MENUorID
- ATL::_U_MENUorID
- _U_MENUorID
dev_langs: C++
helpviewer_keywords:
- U_MENUorID class
- _U_MENUorID class
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7ddde6ff5d45c90e675bd2e44ac421e840d1357b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="umenuorid-class"></a>_U_MENUorID クラス
このクラスのラッパーを提供する**CreateWindow**と**について**です。  
  
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
 この引数のアダプター クラスにより、いずれかの Id ( **UINT**s) またはメニューのハンドル ( `HMENU`s)、呼び出し元の一部で明示的なキャストを必要とせず、関数に渡されます。  
  
 このクラスは、Windows api のラッパーを実装するために設計されていますが、特に[CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)と[について](http://msdn.microsoft.com/library/windows/desktop/ms632680)関数、どちらもそのまま使用、`HMENU`の子になる可能性があります引数ウィンドウの識別子 ( **UINT**) メニューのハンドルではなくです。 たとえばへのパラメーターとしてこのクラスの使用を確認できます[CWindowImpl::Create](cwindowimpl-class.md#create)です。  

  
 2 つのコンス トラクター オーバー ロードがクラスで定義: 1 つを受け入れる、 **UINT**引数で、もう一方を受け入れる、`HMENU`引数。 **UINT**引数にキャスト、`HMENU`コンス トラクターと、クラスの 1 つのデータ メンバーに格納されている結果[m_hMenu](#_u_menuorid__m_hmenu)です。 引数、`HMENU`コンス トラクターは変換せずに直接格納します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h  
  
##  <a name="_u_menuorid__m_hmenu"></a>_U_MENUorID::m_hMenu  
 クラスでは、渡された値をそのコンス トラクターのいずれかとしてパブリック`HMENU`データ メンバーです。  
  
```
HMENU m_hMenu;
```  
  
##  <a name="_u_menuorid___u_menuorid"></a>_U_MENUorID::_U_MENUorID  
 **UINT**引数にキャスト、`HMENU`コンス トラクターと、クラスの 1 つのデータ メンバーに格納されている結果[m_hMenu](#_u_menuorid__m_hmenu)です。  
  
```
_U_MENUorID(UINT nID);  
_U_MENUorID(HMENU hMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 子ウィンドウの識別子。  
  
 `hMenu`  
 メニューのハンドル。  
  
### <a name="remarks"></a>コメント  
 引数、`HMENU`コンス トラクターは変換せずに直接格納します。  
  
## <a name="see-also"></a>参照  
 [クラスの概要](../../atl/atl-class-overview.md)
