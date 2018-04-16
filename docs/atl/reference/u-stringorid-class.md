---
title: "_U_STRINGorID クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL._U_STRINGorID
- ATL::_U_STRINGorID
- _U_STRINGorID
dev_langs:
- C++
helpviewer_keywords:
- _U_STRINGorID class
- U_STRINGorID class
ms.assetid: 443cdc00-d265-4b27-8ef3-2feb95f3e5e3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ebc1b8f65f2a0841baf09b5c95528f571f97ce38
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ustringorid-class"></a>_U_STRINGorID クラス
この引数のアダプター クラスは、いずれかのリソース名を使用できます ( `LPCTSTR`s) またはリソース Id ( **UINT**s)、呼び出し元の ID を使用して文字列を変換を必要とせず、関数に渡される、 **されるときは**マクロです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class _U_STRINGorID
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[_U_STRINGorID::_U_STRINGorID](#_u_stringorid___u_stringorid)|コンストラクターです。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[_U_STRINGorID::m_lpstr](#_u_stringorid__m_lpstr)|リソースの識別子。|  
  
## <a name="remarks"></a>コメント  
 このクラスがなど、Windows リソース管理 API にラッパーを実装するために設計された、 [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042)、 [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072)、および[LoadMenu](http://msdn.microsoft.com/library/windows/desktop/ms647990)を受け入れる関数`LPCTSTR`リソースの名前または ID のいずれかに可能な引数  
  
 2 つのコンス トラクター オーバー ロードがクラスで定義: 1 つを受け入れる、`LPCTSTR`引数で、もう一方を受け入れる、 **UINT**引数。 **UINT**引数を使用して Windows リソース管理機能と互換性のあるリソースの種類に変換、**されるときは**マクロとそのクラスの 1 つのデータ メンバーに格納されている結果[m_lpstr](#_u_stringorid__m_lpstr)です。 引数、`LPCTSTR`コンス トラクターは変換せずに直接格納します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h  
  
##  <a name="_u_stringorid__m_lpstr"></a>_U_STRINGorID::m_lpstr  
 クラスでは、渡された値をそのコンス トラクターのいずれかとしてパブリック`LPCTSTR`データ メンバーです。  
  
```
LPCTSTR m_lpstr;
```  
  
##  <a name="_u_stringorid___u_stringorid"></a>_U_STRINGorID::_U_STRINGorID  
 **UINT**コンス トラクターを使用して Windows リソース管理機能と互換性のあるリソースの種類に引数を変換する、**されるときは**マクロと結果は、クラスの単一の保存データ メンバー、 [m_lpstr](#_u_stringorid__m_lpstr)です。  
  
```
_U_STRINGorID(UINT nID);  
_U_STRINGorID(LPCTSTR lpString);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 リソース id です。  
  
 `lpString`  
 リソースの名前です。  
  
### <a name="remarks"></a>コメント  
 引数、`LPCTSTR`コンス トラクターは変換せずに直接格納します。  
  
## <a name="see-also"></a>参照  
 [クラスの概要](../../atl/atl-class-overview.md)
