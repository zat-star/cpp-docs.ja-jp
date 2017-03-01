---
title: "CMFCTabToolTipInfo 構造 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTabToolTipInfo
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabToolTipInfo struct
ms.assetid: 9c3b3fb9-1497-4d59-932b-0da9348dd5e2
caps.latest.revision: 27
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
ms.openlocfilehash: b9750cd9369313a3ed6ea9474d401cd0068a75fa
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctabtooltipinfo-structure"></a>CMFCTabToolTipInfo 構造体
この構造体は、上、ユーザーがマウスを置いた MDI タブに関する情報を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
struct CMFCTabToolTipInfo  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCTabToolTipInfo::m_nTabIndex](#m_ntabindex)|タブ コントロールのインデックスを指定します。|  
|[CMFCTabToolTipInfo::m_pTabWnd](#m_ptabwnd)|タブ コントロールへのポインター。|  
|[CMFCTabToolTipInfo::m_strText](#m_strtext)|ツールヒントのテキスト。|  
  
## <a name="remarks"></a>コメント  
 ポインター、`CMFCTabToolTipInfo`のパラメーターとして構造体が渡される、`AFX_WM_ON_GET_TAB_TOOLTIP`メッセージです。 MDI タブが有効になっており、タブ コントロール上に置いたときに、このメッセージが生成されます。  
  
## <a name="example"></a>例  
 例を次にどのように`CMFCTabToolTipInfo`で使用される、 [MDITabsDemo サンプル: MFC タブ付き MDI アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_MDITabsDemo&#2;](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CMFCTabToolTipInfo](../../mfc/reference/cmfctabtooltipinfo-structure.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxbasetabctrl.h  
  
##  <a name="a-namemntabindexa--cmfctabtooltipinfomntabindex"></a><a name="m_ntabindex"></a>CMFCTabToolTipInfo::m_nTabIndex  
 タブ コントロールのインデックスを指定します。  
  
```  
int m_nTabIndex;  
```  
  
### <a name="remarks"></a>コメント  
 どのユーザーがマウスを置いたタブのインデックス。  
  
### <a name="example"></a>例  
 例を次にどのように`m_nTabIndex`で使用される、 [MDITabsDemo サンプル: MFC タブ付き MDI アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_MDITabsDemo&#2;](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
##  <a name="a-namemptabwnda--cmfctabtooltipinfomptabwnd"></a><a name="m_ptabwnd"></a>CMFCTabToolTipInfo::m_pTabWnd  
 タブ コントロールへのポインター。  
  
```  
CMFCBaseTabCtrl* m_pTabWnd;  
```  
  
### <a name="example"></a>例  
 例を次にどのように`m_pTabWnd`で使用される、 [MDITabsDemo サンプル: MFC タブ付き MDI アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_MDITabsDemo&#2;](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
##  <a name="a-namemstrtexta--cmfctabtooltipinfomstrtext"></a><a name="m_strtext"></a>CMFCTabToolTipInfo::m_strText  
 ツールヒントのテキスト。  
  
```  
CString m_strText;  
```  
  
### <a name="remarks"></a>コメント  
 文字列が空の場合、ツールヒントが表示されません。  
  
### <a name="example"></a>例  
 例を次にどのように`m_strText`で使用される、 [MDITabsDemo サンプル: MFC タブ付き MDI アプリケーション](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_MDITabsDemo&#2;](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)

