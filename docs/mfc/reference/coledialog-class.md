---
title: "関数クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDialog
- AFXODLGS/COleDialog
- AFXODLGS/COleDialog::GetLastError
dev_langs:
- C++
helpviewer_keywords:
- COleDialog [MFC], GetLastError
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ae60b9e5a0d2e79d2bf6d9cc06eebfa9df0c6e23
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="coledialog-class"></a>関数クラス
OLE のダイアログ ボックスに共通の機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class COleDialog : public CCommonDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleDialog::GetLastError](#getlasterror)|ダイアログ ボックスによって返されたエラー コードを取得します。|  
  
## <a name="remarks"></a>コメント  
 Microsoft Foundation Class ライブラリは、いくつかのクラスから派生した`COleDialog`:  
  
- [メンバー](../../mfc/reference/coleinsertdialog-class.md)  
  
- [メンバー](../../mfc/reference/coleconvertdialog-class.md)  
  
- [メンバー](../../mfc/reference/colechangeicondialog-class.md)  
  
- [関数](../../mfc/reference/colelinksdialog-class.md)  
  
- [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)  
  
- [関数](../../mfc/reference/coleupdatedialog-class.md)  
  
- [関数](../../mfc/reference/colepastespecialdialog-class.md)  
  
- [メンバー](../../mfc/reference/colepropertiesdialog-class.md)  
  
- [メンバー](../../mfc/reference/colechangesourcedialog-class.md)  
  
 OLE に固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `COleDialog`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxodlgs.h  
  
##  <a name="getlasterror"></a>COleDialog::GetLastError  
 呼び出す、`GetLastError`追加のエラー情報を取得するメンバー関数と`DoModal`返します**IDABORT**。  
  
```  
UINT GetLastError() const;  
```  
  
### <a name="return-value"></a>戻り値  
 によって返されるエラー コード`GetLastError`表示される特定のダイアログ ボックスに依存します。  
  
### <a name="remarks"></a>コメント  
 参照してください、`DoModal`固有のエラー メッセージについては、派生クラスでメンバー関数。  
  
## <a name="see-also"></a>参照  
 [CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



