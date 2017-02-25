---
title: "スクロール バー スタイル | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SBS_VERT"
  - "SBS_SIZEBOXBOTTOMRIGHTALIGN"
  - "SBS_LEFTALIGN"
  - "SBS_RIGHTALIGN"
  - "SBS_TOPALIGN"
  - "SBS_SIZEBOXTOPLEFTALIGN"
  - "SBS_BOTTOMALIGN"
  - "SBS_SIZEBOX"
  - "SBS_HORZ"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SBS_BOTTOMALIGN 定数"
  - "SBS_HORZ 定数"
  - "SBS_LEFTALIGN 定数"
  - "SBS_RIGHTALIGN 定数"
  - "SBS_SIZEBOX 定数"
  - "SBS_SIZEBOXBOTTOMRIGHTALIGN 定数"
  - "SBS_SIZEBOXTOPLEFTALIGN 定数"
  - "SBS_TOPALIGN 定数"
  - "SBS_VERT 定数"
  - "スクロール バー, スタイル"
ms.assetid: 8bcde35b-387d-49ae-bdd6-7cda9f5dae26
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# スクロール バー スタイル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **SBS\_BOTTOMALIGN**は  **SBS\_HORZ** のスタイルを使用します。  スクロール バーの右端または下端が **作成** のメンバー関数では、指定された四角形の下端に合わせて配置します。  スクロール バーでスクロール バー システムの既定の高さがあります。  
  
-   **SBS\_HORZ**は水平スクロール バーを指定します。  **SBS\_BOTTOMALIGN** が **SBS\_TOPALIGN** のスタイルも指定しない場合、スクロール バーに指定 **作成** のメンバー関数の高さ、幅、および位置があります。  
  
-   **SBS\_LEFTALIGN**は  **SBS\_VERT** のスタイルを使用します。  スクロール バーの左端が **作成** のメンバー関数では、指定された四角形の左端に揃えられます。  スクロール バーでスクロール バー システムの既定の幅があります。  
  
-   **SBS\_RIGHTALIGN**は  **SBS\_VERT** のスタイルを使用します。  スクロール バーの右端が **作成** のメンバー関数では、指定された四角形の右端に揃えられます。  スクロール バーでスクロール バー システムの既定の幅があります。  
  
-   **SBS\_SIZEBOX**はサイズ ボックスを指定します。  **SBS\_SIZEBOXBOTTOMRIGHTALIGN** が **SBS\_SIZEBOXTOPLEFTALIGN** のスタイルも指定しない場合、サイズ ボックスに指定 **作成** のメンバー関数の高さ、幅、および位置があります。  
  
-   **SBS\_SIZEBOXBOTTOMRIGHTALIGN**は  **SBS\_SIZEBOX** のスタイルを使用します。  サイズ ボックスの右下隅に **作成** のメンバー関数では、指定された四角形の右下隅に配置します。  サイズ ボックスにシステム サイズ ボックスの既定のサイズになります。  
  
-   **SBS\_SIZEBOXTOPLEFTALIGN**は  **SBS\_SIZEBOX** のスタイルを使用します。  サイズ ボックスの左上隅に **作成** のメンバー関数では、指定された四角形の左上隅に配置されます。  サイズ ボックスにシステム サイズ ボックスの既定のサイズになります。  
  
-   **SBS\_SIZEGRIP** 浮き出しな端に対する **SBS\_SIZEBOX**と同様ですが。  
  
-   **SBS\_TOPALIGN**は  **SBS\_HORZ** のスタイルを使用します。  スクロール バーの上端に **作成** のメンバー関数では、指定された四角形の上端に揃えられます。  スクロール バーでスクロール バー システムの既定の高さがあります。  
  
-   **SBS\_VERT**は垂直スクロール バーを指定します。  **SBS\_RIGHTALIGN** が **SBS\_LEFTALIGN** のスタイルも指定しない場合、スクロール バーに指定 **作成** のメンバー関数の高さ、幅、および位置があります。  
  
## 参照  
 [MFC で使用するスタイル](../../mfc/reference/styles-used-by-mfc.md)   
 [CScrollBar::Create](../Topic/CScrollBar::Create.md)   
 [Scroll Bar Control Styles](http://msdn.microsoft.com/library/windows/desktop/bb787533)