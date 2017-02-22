---
title: "PAINTSTRUCT 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PAINTSTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PAINTSTRUCT 構造体"
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# PAINTSTRUCT 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`PAINTSTRUCT` 構造体は、ウィンドウのクライアント領域を描画するために使用できる情報が含まれます。  
  
## 構文  
  
```  
  
      typedef struct tagPAINTSTRUCT {  
   HDC hdc;  
   BOOL fErase;  
   RECT rcPaint;  
   BOOL fRestore;  
   BOOL fIncUpdate;  
   BYTE rgbReserved[16];  
} PAINTSTRUCT;  
```  
  
#### パラメーター  
 *hdc*  
 描画に使用するコンテキストを指定します。  
  
 *fErase*  
 背景が再描画される必要があるかどうかを指定します。  アプリケーションが背景を再描画すれば 0 ではありません。  アプリケーションは、Windows のウィンドウ クラスの背景ブラシなしで作成された背景を描画する必要があります \([!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) 構造体の **hbrBackground** のメンバーの説明を参照してください。  
  
 *rcPaint*  
 描画が要求される四角形の左上、右下隅を指定します。  
  
 *fRestore*  
 予約済みのメンバー。  これは Windows で内部的に使用されます。  
  
 *fIncUpdate*  
 予約済みのメンバー。  これは Windows で内部的に使用されます。  
  
 *rgbReserved\[16\]*  
 予約済みのメンバー。  Windows によって内部的に使用されるメモリの予約ブロック。  
  
## 必要条件  
 **ヘッダー:** winuser.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPaintDC::m\_ps](../Topic/CPaintDC::m_ps.md)