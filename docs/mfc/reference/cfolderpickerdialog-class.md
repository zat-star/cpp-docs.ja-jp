---
title: "CFolderPickerDialog クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog::CFolderPickerDialog
dev_langs:
- C++
helpviewer_keywords:
- CFolderPickerDialog class
ms.assetid: 8db01684-dd1d-4e9c-989e-07a2318a8156
caps.latest.revision: 22
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
ms.openlocfilehash: 0d020544a16056d3f4db538750ed5a16b54f9a51
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cfolderpickerdialog-class"></a>CFolderPickerDialog クラス
CFolderPickerDialog クラスは、フォルダー ピッカー モードの CFileDialog を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CFolderPickerDialog : public CFileDialog;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFolderPickerDialog:: ~ CFolderPickerDialog](#cfolderpickerdialog__~cfolderpickerdialog)|デストラクターです。|  
|[CFolderPickerDialog::CFolderPickerDialog](#cfolderpickerdialog)|コンストラクターです。|  
  
## <a name="remarks"></a>コメント  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [CFileDialog](../../mfc/reference/cfiledialog-class.md)  
  
 `CFolderPickerDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdlgs.h  
  
##  <a name="cfolderpickerdialog"></a>CFolderPickerDialog::CFolderPickerDialog  
 コンストラクターです。  
  
```  
explicit CFolderPickerDialog(
    LPCTSTR lpszFolder = NULL,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL,  
    DWORD dwSize = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFolder`  
 初期のフォルダー。  
  
 `dwFlags`  
 ダイアログ ボックスをカスタマイズするための&1; つまたは複数のフラグの組み合わせ。  
  
 `pParentWnd`  
 ダイアログ ボックス オブジェクトの親ウィンドウまたはオーナー ウィンドウへのポインター。  
  
 `dwSize`  
 OPENFILENAME 構造体のサイズ。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="_dtorcfolderpickerdialog"></a>CFolderPickerDialog:: ~ CFolderPickerDialog  
 デストラクターです。  
  
```  
virtual ~CFolderPickerDialog();
```  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

