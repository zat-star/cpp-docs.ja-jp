---
title: "CWinTraitsOR クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR::GetWndExStyle
- ATLWIN/ATL::CWinTraitsOR::GetWndStyle
dev_langs:
- C++
helpviewer_keywords:
- CWinTraitsOR class
- window styles, default values for ATL
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: cd077c7f79c3099d0e825a48233e7a8b269c0d04
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cwintraitsor-class"></a>CWinTraitsOR クラス
このクラスは、ウィンドウ オブジェクトの作成時に使用するスタイルを標準化するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <DWORD t_dwStyle = 0,
          DWORD t_dwExStyle = 0, 
          class TWinTraits = CControlWinTraits>
class CWinTraitsOR
```  
  
#### <a name="parameters"></a>パラメーター  
 `t_dwStyle`  
 既定のウィンドウ スタイル。  
  
 `t_dwExStyle`  
 拡張ウィンドウ スタイルを既定値です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWinTraitsOR::GetWndExStyle](#getwndexstyle)|拡張スタイルを取得、`CWinTraitsOR`オブジェクトです。|  
|[CWinTraitsOR::GetWndStyle](#getwndstyle)|標準のスタイルを取得、`CWinTraitsOR`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 これは、[ウィンドウの特徴](../../atl/understanding-window-traits.md)クラスには、ATL ウィンドウ オブジェクトの作成に使用するスタイルを標準化するための簡単な方法が用意されています。 このクラスの特殊化を使用するテンプレート パラメーターとして[CWindowImpl](../../atl/reference/cwindowimpl-class.md)または別の最小値に使用される標準および拡張スタイルを指定するのには、ATL のウィンドウ クラスのウィンドウ クラスのインスタンス。  
  
 特定のスタイル設定されているウィンドウ クラスのすべてのインスタンスの他のスタイルを確保しながら呼び出しでは、インスタンスごとの単位で設定することを確認する場合は、このテンプレートの特殊化を使用して[CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create)します。  
  
 既定の呼び出しでは、その他のスタイルが指定されていない場合にのみ使用されるウィンドウ スタイルを指定する場合は、`CWindowImpl::Create`を使用して[CWinTraits](../../atl/reference/cwintraits-class.md)代わりにします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="getwndstyle"></a>CWinTraitsOR::GetWndStyle  
 (論理 OR 演算子を使用して) の標準的なスタイルの組み合わせを取得するには、この関数を呼び出して、`CWinTraits`オブジェクトと既定のスタイルで指定された`t_dwStyle`します。  
  
```
static DWORD GetWndStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 スタイルのウィンドウの作成に使用します。  
  
### <a name="return-value"></a>戻り値  
 渡されるスタイルの組み合わせ`dwStyle`と既定値で指定されたもの`t_dwStyle`、論理 OR 演算子を使用します。  
  
##  <a name="getwndexstyle"></a>CWinTraitsOR::GetWndExStyle  
 (論理 OR 演算子を使用して) の拡張スタイルの組み合わせを取得するには、この関数を呼び出して、`CWinTraits`オブジェクトと既定のスタイルで指定された`t_dwStyle`します。  
  
```
static DWORD GetWndExStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwExStyle`  
 拡張スタイルのウィンドウの作成に使用します。  
  
### <a name="return-value"></a>戻り値  
 渡された拡張スタイルを組み合わせた`dwExStyle`デフォルトで指定された値と`t_dwExStyle`、論理 OR 演算子を使用します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [ウィンドウの特徴を理解します。](../../atl/understanding-window-traits.md)


