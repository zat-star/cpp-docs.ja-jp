---
title: "クラスの関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDialog
dev_langs:
- C++
helpviewer_keywords:
- OLE dialog boxes, base class
- dialog boxes, OLE
- COleDialog class
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
caps.latest.revision: 21
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 018d06ac167a8c352d9f1822b373126c4e615854
ms.lasthandoff: 02/24/2017

---
# <a name="coledialog-class"></a>関数のクラス
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
  
 OLE 固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `COleDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxodlgs.h  
  
##  <a name="a-namegetlasterrora--coledialoggetlasterror"></a><a name="getlasterror"></a>COleDialog::GetLastError  
 呼び出す、`GetLastError`追加のエラー情報を取得するメンバー関数と`DoModal`を返します**IDABORT**します。  
  
```  
UINT GetLastError() const;  
```  
  
### <a name="return-value"></a>戻り値  
 によって返されるエラー コード`GetLastError`表示される特定のダイアログ ボックスに依存します。  
  
### <a name="remarks"></a>コメント  
 参照してください、`DoModal`具体的なエラー メッセージについては、派生クラスのメンバー関数。  
  
## <a name="see-also"></a>関連項目  
 [CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)




