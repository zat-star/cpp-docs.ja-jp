---
title: "CWinTraits クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinTraits
- ATLWIN/ATL::CWinTraits
- ATLWIN/ATL::CWinTraits::GetWndExStyle
- ATLWIN/ATL::CWinTraits::GetWndStyle
dev_langs:
- C++
helpviewer_keywords:
- CMDIChildWinTraits class
- window styles, default values for ATL
- CWinTraits class
- CFrameWinTraits class
- CControlWinTraits class
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: abd62b916f976721bf85fc4bb2a94ffaf5b217ea
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cwintraits-class"></a>CWinTraits クラス
このクラスは、ウィンドウ オブジェクトの作成時に使用するスタイルを標準化するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <DWORD t_dwStyle = 0, DWORD t_dwExStyle = 0>  class CWinTraits
```  
  
#### <a name="parameters"></a>パラメーター  
 `t_dwStyle`  
 既定の標準的なウィンドウ スタイル。  
  
 `t_dwExStyle`  
 拡張ウィンドウ スタイルを既定値です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWinTraits::GetWndExStyle](#getwndexstyle)|(静的)拡張スタイルを取得、`CWinTraits`オブジェクトです。|  
|[CWinTraits::GetWndStyle](#getwndstyle)|(静的)標準のスタイルを取得、`CWinTraits`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 これは、[ウィンドウの特徴](../../atl/understanding-window-traits.md)クラスには、ATL ウィンドウ オブジェクトの作成に使用するスタイルを標準化するための簡単な方法が用意されています。 テンプレートのパラメーターとしてこのクラスの特殊化を使用して[CWindowImpl](../../atl/reference/cwindowimpl-class.md)または別に使用される既定の標準および拡張スタイルを指定する、ATL のウィンドウ クラスのウィンドウ クラスのインスタンス。  
  
 既定の呼び出しでは、その他のスタイルが指定されていない場合にのみ使用されるウィンドウ スタイルを指定する場合に、このテンプレートを使用して[CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create)します。  
  
 ATL には、このテンプレートをウィンドウ スタイルの一般的に使用される組み合わせの&3; つの定義済み特殊化が用意されています。  
  
 `CControlWinTraits`  
 標準コントロール ウィンドウの設計されています。 次の標準的なスタイルを使用して: **WS_CHILD**、 **WS_VISIBLE**、 **WS_CLIPCHILDREN**、および**WS_CLIPSIBLINGS**します。 拡張スタイルはありません。  
  
 `CFrameWinTraits`  
 標準のフレーム ウィンドウ用に設計されています。 使用される標準のスタイルを含める: **WS_OVERLAPPEDWINDOW**、 **WS_CLIPCHILDREN**、および**WS_CLIPSIBLINGS**します。 使用されている拡張スタイルを含める: **WS_EX_APPWINDOW**と**WS_EX_WINDOWEDGE**します。  
  
 `CMDIChildWinTraits`  
 標準的な MDI 子ウィンドウの設計されています。 使用される標準のスタイルを含める: **WS_OVERLAPPEDWINDOW**、 **WS_CHILD**、 **WS_VISIBLE**、 **WS_CLIPCHILDREN**、および**WS_CLIPSIBLINGS**します。 使用されている拡張スタイルを含める: **WS_EX_MDICHILD**します。  
  
 インスタンスごとの単位で設定するには、その他のスタイルを確保しながら、ウィンドウ クラスのすべてのインスタンスを使用して特定のスタイルが設定されていることを確認する場合は、 [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md)代わりにします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="getwndstyle"></a>CWinTraits::GetWndStyle  
 標準的なスタイルを取得するには、この関数を呼び出して、`CWinTraits`オブジェクトです。  
  
```
static DWORD GetWndStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 標準的なスタイルのウィンドウの作成に使用します。 場合`dwStyle`は 0、テンプレートのスタイル値 ( `t_dwStyle`) が返されます。 場合`dwStyle`がゼロ以外、`dwStyle`が返されます。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトの標準のウィンドウ スタイル。  
  
##  <a name="getwndexstyle"></a>CWinTraits::GetWndExStyle  
 拡張スタイルを取得するには、この関数を呼び出して、`CWinTraits`オブジェクトです。  
  
```
static DWORD GetWndExStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwExStyle`  
 拡張スタイルのウィンドウの作成に使用します。 場合`dwExStyle`は 0、テンプレートのスタイル値 ( `t_dwExStyle`) が返されます。 場合`dwExStyle`がゼロ以外、`dwExStyle`が返されます。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトの拡張ウィンドウ スタイル。  
  
## <a name="see-also"></a>関連項目  
 [クラス メンバー](http://msdn.microsoft.com/en-us/dbe6a147-3f01-4aea-a3fb-fe6ebadc31f8)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [ウィンドウの特徴を理解します。](../../atl/understanding-window-traits.md)

