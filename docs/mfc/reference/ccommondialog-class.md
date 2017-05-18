---
title: "CCommonDialog クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCommonDialog
- AFXDLGS/CCommonDialog
- AFXDLGS/CCommonDialog::CCommonDialog
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [C++], Windows common dialogs
- common dialog boxes [C++], common dialog classes
- common dialog classes [C++]
- MFC dialog boxes, Windows common dialogs
- Windows common dialogs [C++]
- CCommonDialog class
- dialog classes [C++], common
ms.assetid: 1f68d65f-a0fd-4778-be22-ebbe51a95f95
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 93d4cd4ca794095c225641bc67353b9a53080c3c
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ccommondialog-class"></a>CCommonDialog クラス
Windows コモン ダイアログの機能をカプセル化したクラスの基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CCommonDialog : public CDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CCommonDialog::CCommonDialog](#ccommondialog)|`CCommonDialog` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 次のクラスには、Windows のコモン ダイアログの機能がカプセル化します。  
  
- [CFileDialog](../../mfc/reference/cfiledialog-class.md)  
  
- [CFontDialog](../../mfc/reference/cfontdialog-class.md)  
  
- [CColorDialog](../../mfc/reference/ccolordialog-class.md)  
  
- [メンバー](../../mfc/reference/cpagesetupdialog-class.md)  
  
- [CPrintDialog](../../mfc/reference/cprintdialog-class.md)  
  
- [メンバー](../../mfc/reference/cprintdialogex-class.md)  
  
- [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md)  
  
- [関数](../../mfc/reference/coledialog-class.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CCommonDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdlgs.h  
  
##  <a name="ccommondialog"></a>CCommonDialog::CCommonDialog  
 `CCommonDialog` オブジェクトを構築します。  
  
```  
explicit CCommonDialog(CWnd* pParentWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 親またはオーナー ウィンドウのオブジェクトを指します (型の[CWnd](../../mfc/reference/cwnd-class.md)) ダイアログ オブジェクトが属しています。 ある場合**NULL**、ダイアログ オブジェクトの親ウィンドウがアプリケーションのメイン ウィンドウに設定します。  
  
### <a name="remarks"></a>コメント  
 参照してください[詳細](../../mfc/reference/cdialog-class.md#cdialog)の詳細について。  
  
## <a name="see-also"></a>関連項目  
 [CDialog クラス](../../mfc/reference/cdialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)   
 [CFontDialog クラス](../../mfc/reference/cfontdialog-class.md)   
 [CColorDialog クラス](../../mfc/reference/ccolordialog-class.md)   
 [メンバー クラス](../../mfc/reference/cpagesetupdialog-class.md)   
 [CPrintDialog クラス](../../mfc/reference/cprintdialog-class.md)   
 [CFindReplaceDialog クラス](../../mfc/reference/cfindreplacedialog-class.md)   
 [関数のクラス](../../mfc/reference/coledialog-class.md)

