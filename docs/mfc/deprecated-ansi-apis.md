---
title: "サポートされなくなった ANSI API | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC, 使用を推奨されていない ANSI メソッド"
ms.assetid: c7c5a6fd-95e4-4bee-b3d5-d3826c30947d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# サポートされなくなった ANSI API
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft Foundation Class \(MFC\) ライブラリは、Unicode 文字セットに基づくメソッドおよびクラスの方向に移行します。  したがって、複数の MFC メソッドの ANSI バージョンの使用は推奨されていません。  今後のアプリケーションでは、これらのメソッドの Unicode バージョンを使用します。  
  
 [!INCLUDE[windowsver](../Token/windowsver_md.md)]に付属する Windows コモン コントロール Version 6.1 以降では、次の ANSI メソッドの使用は推奨されていません。  
  
## CButton クラス  
  
```  
AFX_ANSI_DEPRECATED BOOL GetIdealSize(LPSIZE psize) const;  
AFX_ANSI_DEPRECATED BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist) const;  
AFX_ANSI_DEPRECATED BOOL GetTextMargin(LPRECT pmargin) const;  
AFX_ANSI_DEPRECATED BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);  
AFX_ANSI_DEPRECATED BOOL SetTextMargin(LPRECT pmargin);  
```  
  
## CComboBoxEx クラス  
  
```  
AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);  
```  
  
## CEdit クラス  
  
```  
AFX_ANSI_DEPRECATED BOOL GetCueBanner(LPWSTR lpszText, int cchText) const;  
AFX_ANSI_DEPRECATED BOOL SetCueBanner(LPCWSTR lpszText, BOOL fDrawIfFocused = FALSE);  
```  
  
## CLinkCtrl クラス  
 クラス全体の使用は推奨されていません。  
  
## CListCtrl クラス  
  
```  
AFX_ANSI_DEPRECATED void CancelEditLabel();  
AFX_ANSI_DEPRECATED int EnableGroupView(BOOL fEnable);  
AFX_ANSI_DEPRECATED int GetGroupInfo(int iGroupId, PLVGROUP pgrp) const;  
AFX_ANSI_DEPRECATED void GetGroupMetrics(PLVGROUPMETRICS pGroupMetrics) const;  
AFX_ANSI_DEPRECATED BOOL GetInsertMark(LPLVINSERTMARK lvim) const;  
AFX_ANSI_DEPRECATED COLORREF GetInsertMarkColor() const;  
AFX_ANSI_DEPRECATED int GetInsertMarkRect(LPRECT pRect) const;  
AFX_ANSI_DEPRECATED COLORREF GetOutlineColor() const;  
AFX_ANSI_DEPRECATED UINT GetSelectedColumn() const;  
AFX_ANSI_DEPRECATED BOOL GetTileInfo(PLVTILEINFO pti) const;  
AFX_ANSI_DEPRECATED BOOL GetTileViewInfo(PLVTILEVIEWINFO ptvi) const;  
AFX_ANSI_DEPRECATED DWORD GetView() const;  
AFX_ANSI_DEPRECATED BOOL HasGroup(int iGroupId) const;  
AFX_ANSI_DEPRECATED int InsertGroup(int index, PLVGROUP pgrp);  
AFX_ANSI_DEPRECATED void InsertGroupSorted(PLVINSERTGROUPSORTED pStructInsert);  
AFX_ANSI_DEPRECATED int InsertMarkHitTest(LPPOINT pPoint, LPLVINSERTMARK lvim) const;  
AFX_ANSI_DEPRECATED BOOL IsGroupViewEnabled() const;  
AFX_ANSI_DEPRECATED void MoveGroup(int iGroupId, int toIndex);  
AFX_ANSI_DEPRECATED void MoveItemToGroup(int idItemFrom, int idGroupTo);  
AFX_ANSI_DEPRECATED void RemoveAllGroups();  
AFX_ANSI_DEPRECATED int RemoveGroup(int iGroupId);  
AFX_ANSI_DEPRECATED BOOL SetGroupInfo(int iGroupId, PLVGROUP pGroup);  
AFX_ANSI_DEPRECATED void SetGroupMetrics(PLVGROUPMETRICS pGroupMetrics);  
AFX_ANSI_DEPRECATED BOOL SetInfoTip(PLVSETINFOTIP plvInfoTip);  
AFX_ANSI_DEPRECATED BOOL SetInsertMark(LPLVINSERTMARK lvim);  
AFX_ANSI_DEPRECATED COLORREF SetInsertMarkColor(COLORREF color);  
AFX_ANSI_DEPRECATED COLORREF SetOutlineColor(COLORREF color);  
AFX_ANSI_DEPRECATED void SetSelectedColumn(int iCol);  
AFX_ANSI_DEPRECATED BOOL SetTileInfo(PLVTILEINFO pti);  
AFX_ANSI_DEPRECATED BOOL SetTileViewInfo(PLVTILEVIEWINFO ptvi);  
AFX_ANSI_DEPRECATED DWORD SetView(int iView);  
AFX_ANSI_DEPRECATED BOOL SortGroups(PFNLVGROUPCOMPARE _pfnGroupCompare, LPVOID _plv);  
```  
  
## CReBarCtrl クラス  
  
```  
AFX_ANSI_DEPRECATED void GetBandMargins(PMARGINS pMargins) const;  
AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);  
```  
  
## CToolBarCtrl クラス  
  
```  
AFX_ANSI_DEPRECATED void GetMetrics(LPTBMETRICS ptbm) const;  
AFX_ANSI_DEPRECATED void SetMetrics(LPTBMETRICS ptbm);  
AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);  
```  
  
## CToolTipCtrl Class  
  
```  
AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);  
```  
  
## 参照  
 [Windows Vista コモン コントロールの作成要件](../mfc/build-requirements-for-windows-vista-common-controls.md)