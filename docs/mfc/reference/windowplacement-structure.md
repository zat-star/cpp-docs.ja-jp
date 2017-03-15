---
title: "WINDOWPLACEMENT 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WINDOWPLACEMENT
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPLACEMENT structure
ms.assetid: ea7d61f6-eb57-478e-9b08-7c1d07091aa8
caps.latest.revision: 11
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 62cf7003f43d50d5998dd527ae5ad7b10ab95686
ms.lasthandoff: 02/24/2017

---
# <a name="windowplacement-structure"></a>WINDOWPLACEMENT 構造体
`WINDOWPLACEMENT`構造体には、画面上のウィンドウの配置についての情報が含まれています。**します。**  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagWINDOWPLACEMENT {     /* wndpl */  
    UINT length;  
    UINT flags;  
    UINT showCmd;  
    POINT ptMinPosition;  
    POINT ptMaxPosition;  
    RECT rcNormalPosition;  
} WINDOWPLACEMENT;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *length*  
 構造体のバイト単位で長さを指定**します。**  
  
 `flags`  
 最小化されたウィンドウとウィンドウを復元する方法の位置を制御するフラグを指定します。 このメンバーは、次のフラグの一方または両方を指定できます。  
  
- **WPF_SETMINPOSITION**最小化されたウィンドウの x 位置と y 位置を指定できることを示す**します。** このフラグである必要があります指定された座標で設定されているかどうか、 **ptMinPosition**メンバーです。  
  
- **WPF_RESTORETOMAXIMIZED**復元されたウィンドウが最大化される、最小化する前に、最大化されていたかどうかに関係なくを指定します。 この設定は、ウィンドウを閉じたときにのみ有効です。 既定の復元動作は変わりません。 このフラグは有効な場合にのみ、**このメンバーは**値が指定されて、 **showCmd**メンバーです。  
  
 *showCmd*  
 ウィンドウの現在の表示状態を指定します。 このメンバーは、次の値のいずれかになります。  
  
- **SW_HIDE**ウィンドウを非表示にし、別のウィンドウをアクティブ化を渡します。  
  
- **SW_MINIMIZE**指定されたウィンドウを最小化し、システムの一覧の最上位ウィンドウを表示します。  
  
- **SW_RESTORE**にアクティブとウィンドウが表示されます。 ウィンドウが最小化または最大化されている場合は、Windows が復元され、元のサイズと位置 (同じ**SW_SHOWNORMAL**)。  
  
- **SW_SHOW**ウィンドウをアクティブにし、現在のサイズと位置に表示されます。  
  
- **SW_SHOWMAXIMIZED**ウィンドウをアクティブにし、最大化されたウィンドウとして表示されます。  
  
- **このメンバーは**ウィンドウをアクティブにし、アイコンとして表示します。  
  
- **SW_SHOWMINNOACTIVE**ウィンドウをアイコンとして表示します。 現在アクティブなウィンドウは、アクティブなままです。  
  
- **SW_SHOWNA**現在の状態で、ウィンドウを表示します。 現在アクティブなウィンドウは、アクティブなままです。  
  
- **SW_SHOWNOACTIVATE**最新のサイズと位置で、ウィンドウを表示します。 現在アクティブなウィンドウは、アクティブなままです。  
  
- **SW_SHOWNORMAL**にアクティブとウィンドウが表示されます。 ウィンドウが最小化または最大化されている場合は、Windows が復元され、元のサイズと位置 (同じ**SW_RESTORE**)。  
  
 *ptMinPosition*  
 ウィンドウが最小化されているときは、ウィンドウの左上隅の位置を指定します。  
  
 `ptMaxPosition`  
 ウィンドウを最大化するときは、ウィンドウの左上隅の位置を指定します。  
  
 *rcNormalPosition*  
 ウィンドウが標準の (復元) の位置にある場合は、ウィンドウの座標を指定します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::SetWindowPlacement](../../mfc/reference/cwnd-class.md#setwindowplacement)


