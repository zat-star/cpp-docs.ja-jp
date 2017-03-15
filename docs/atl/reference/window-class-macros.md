---
title: "ウィンドウ クラスに関するマクロ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: ce18681a-2bab-4453-9895-0f3ea47c2b24
caps.latest.revision: 16
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
ms.sourcegitcommit: 8cdedc5cfac9d49df812ae6fcfcc548201b1edb5
ms.openlocfilehash: f32926b6efd4ffb9c0541c0574a479c13dac01df
ms.lasthandoff: 02/24/2017

---
# <a name="window-class-macros"></a>ウィンドウ クラスに関するマクロ
これらのマクロは、ウィンドウ クラスのユーティリティを定義します。  
  
|||  
|-|-|  
|[DECLARE_WND_CLASS](#declare_wnd_class)|新しいウィンドウ クラスの名前を指定できます。| 
|[DECLARE_WND_CLASS2](#declare_wnd_class2)|(Visual Studio 2017)新しいウィンドウ クラスと新しいクラスが使用するウィンドウ プロシージャの外側のクラスの名前を指定できます。| 
|[DECLARE_WND_SUPERCLASS](#declare_wnd_superclass)|新しいウィンドウ クラスの基になる既存のウィンドウ クラスの名前を指定できます。|  
|[場合は](#declare_wnd_class_ex)|クラスのパラメーターを指定できます。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
   
##  <a name="a-namedeclarewndclassa--declarewndclass"></a><a name="declare_wnd_class"></a>DECLARE_WND_CLASS  
 新しいウィンドウ クラスの名前を指定できます。 ATL の ActiveX コントロールのコントロール クラスには、このマクロを配置します。  
  
```
DECLARE_WND_CLASS( WndClassName )
```  
  
### <a name="parameters"></a>パラメーター  
 `WndClassName`  
 [in]新しいウィンドウ クラスの名前。 場合**NULL**、ATL ウィンドウ クラス名が生成されます。  
  
### <a name="remarks"></a>コメント  
 /Permissive-compiler オプションを使用している場合、DECLARE_WND_CLASS、コンパイラ エラーが発生します。DECLARE_WND_CLASS2 を使用してください。
 
 によって管理される情報を新しいウィンドウ クラスの名前を指定することにより、DECLARE_WND_CLASS [CWndClassInfo](cwndclassinfo-class.md)します。 `DECLARE_WND_CLASS`次の静的関数を実装することで、新しいウィンドウ クラスを定義します。  
  
 [!code-cpp[NVC_ATL_Windowing&#127;](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 `DECLARE_WND_CLASS`新しいウィンドウの次のスタイルを指定します。  
  
-   CS_HREDRAW  
  
-   CS_VREDRAW  
  
-   CS_DBLCLKS  
  
 `DECLARE_WND_CLASS`また、既定のウィンドウの背景色を指定します。 使用して、[場合は](#declare_wnd_class_ex)マクロを独自のスタイルを提供し、背景色。  
  
 [CWindowImpl](cwindowimpl-class.md)を使用して、`DECLARE_WND_CLASS`ウィンドウを作成するマクロが新しいウィンドウ クラスに基づいています。 この動作を上書きするには、使用、 [DECLARE_WND_SUPERCLASS](#declare_wnd_superclass)マクロ、または独自の実装を提供する、 [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo)関数です。  

  
 詳細については、ATL でのウィンドウを使用して、記事を参照してください。 [ATL ウィンドウ クラス](../../atl/atl-window-classes.md)します。  

##  <a name="a-namedeclarewndclass2a--declarewndclass2"></a><a name="declare_wnd_class2"></a>DECLARE_WND_CLASS2  
 (Visual Studio 2017)DECLARE_WND_CLASS には、/permissive-option でコンパイルすると、依存名エラーの発生を回避する追加のパラメーターと同じです。
  
```
DECLARE_WND_CLASS2( WndClassName, EnclosingClass )
```  
  
### <a name="parameters"></a>パラメーター  
 `WndClassName`  
 [in]新しいウィンドウ クラスの名前。 場合**NULL**、ATL ウィンドウ クラス名が生成されます。 

 `EnclosingClass`  
 [in]新しいウィンドウ クラスを囲むウィンドウ クラスの名前。 ことはできません**NULL**します。  
  
### <a name="remarks"></a>コメント 
/Permissive-option を使用している場合、DECLARE_WND_CLASS と、コンパイル エラーが依存している名前が含まれています。 DECLARE_WND_CLASS2 では、このマクロが使用され、下にある、/permissive-flag エラーは発生しませんクラスを明示的に名前を付ける必要があります。
このマクロは、それ以外の場合と同じ[DECLARE_WND_CLASS](#declare_wnd_class)します。
   
##  <a name="a-namedeclarewndsuperclassa--declarewndsuperclass"></a><a name="declare_wnd_superclass"></a>DECLARE_WND_SUPERCLASS  
 クラスのパラメーターを指定できます。 ATL の ActiveX コントロールのコントロール クラスには、このマクロを配置します。  
  
```
DECLARE_WND_SUPERCLASS( WndClassName, OrigWndClassName )
```  
  
### <a name="parameters"></a>パラメーター  
 `WndClassName`  
 [in]ウィンドウの名前のクラスがそのスーパークラス`OrigWndClassName`します。 場合**NULL**、ATL ウィンドウ クラス名が生成されます。  
  
 `OrigWndClassName`  
 [in]既存のウィンドウ クラスの名前。  
  
### <a name="remarks"></a>コメント  
 このマクロでは、ウィンドウ クラスをスーパークラス化する既存のウィンドウ クラスの名前を指定することができます。 [CWndClassInfo](cwndclassinfo-class.md)スーパークラスの情報を管理します。  
  
 `DECLARE_WND_SUPERCLASS`次の静的関数を実装します。  
  
 [!code-cpp[NVC_ATL_Windowing&#127;](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 既定では、 [CWindowImpl](cwindowimpl-class.md)を使用して、 [DECLARE_WND_CLASS](#declare_wnd_class)ウィンドウを作成するマクロが新しいウィンドウ クラスに基づいています。 指定して、`DECLARE_WND_SUPERCLASS`マクロで、`CWindowImpl`の派生クラスでは、ウィンドウ クラスは、既存のクラスに基づきますが、ウィンドウ プロシージャを使用します。 この手法をスーパークラス化と呼びます。  
  
 使用するだけでなく、`DECLARE_WND_CLASS`と`DECLARE_WND_SUPERCLASS`マクロをオーバーライドできます、 [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo)独自の実装を持つ関数です。  

  
 詳細については、ATL でのウィンドウを使用して、記事を参照してください。 [ATL ウィンドウ クラス](../../atl/atl-window-classes.md)します。  
  
##  <a name="a-namedeclarewndclassexa--declarewndclassex"></a><a name="declare_wnd_class_ex"></a>場合は  
 新しいウィンドウ クラスの基になる既存のウィンドウ クラスの名前を指定できます。 ATL の ActiveX コントロールのコントロール クラスには、このマクロを配置します。  
  
```
DECLARE_WND_CLASS_EX( WndClassName, style, bkgnd )
```  
  
### <a name="parameters"></a>パラメーター  
 `WndClassName`  
 [in]新しいウィンドウ クラスの名前。 場合**NULL**、ATL ウィンドウ クラス名が生成されます。  
  
 `style`  
 [in]ウィンドウのスタイル。  
  
 *背景*  
 [in]ウィンドウの背景色。  
  
### <a name="remarks"></a>コメント  
 このマクロでは、によって管理される情報を含む、新しいウィンドウ クラスのクラスのパラメーターを指定できます。 [CWndClassInfo](cwndclassinfo-class.md)します。 `DECLARE_WND_CLASS_EX`次の静的関数を実装することで、新しいウィンドウ クラスを定義します。  
  
 [!code-cpp[NVC_ATL_Windowing&#127;](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]  
  
 既定のスタイルと背景色を使用する場合を使用して、 [DECLARE_WND_CLASS](#declare_wnd_class)マクロです。 詳細については、ATL でのウィンドウを使用して、記事を参照してください。 [ATL ウィンドウ クラス](../../atl/atl-window-classes.md)します。  
  
## <a name="see-also"></a>関連項目  
 [マクロ](atl-macros.md)










