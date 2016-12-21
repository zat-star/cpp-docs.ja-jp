---
title: "CWndClassInfo クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWndClassInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWndClassInfo クラス"
ms.assetid: c36fe7e1-75f1-4cf5-a06f-9f59c43fe6fb
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWndClassInfo クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、ウィンドウ クラスの情報を登録するためのメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CWndClassInfo  
  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|||  
|-|-|  
|[登録](../Topic/CWndClassInfo::Register.md)|ウィンドウ クラスを登録します。|  
  
### データ メンバー  
  
|||  
|-|-|  
|[m\_atom](../Topic/CWndClassInfo::m_atom.md)|登録されたウィンドウ クラスを識別します。|  
|[m\_bSystemCursor](../Topic/CWndClassInfo::m_bSystemCursor.md)|カーソル リソースがモジュールのリソースに含まれているカーソルのシステムのカーソルを参照するかどうかを指定します。|  
|[m\_lpszCursorID](../Topic/CWndClassInfo::m_lpszCursorID.md)|カーソル リソースの名前を指定します。|  
|[m\_lpszOrigName](../Topic/CWndClassInfo::m_lpszOrigName.md)|既存のウィンドウ クラスの名前が含まれています。|  
|[m\_szAutoName](../Topic/CWndClassInfo::m_szAutoName.md)|生成された ATL ウィンドウ クラスの名前を保持します。|  
|[m\_wc](../Topic/CWndClassInfo::m_wc.md)|**WNDCLASSEX** の構造のウィンドウ クラスの情報を保持します。|  
|[pWndProc](../Topic/CWndClassInfo::pWndProc.md)|既存のウィンドウ クラスのウィンドウ プロシージャへのポインター。|  
  
## 解説  
 `CWndClassInfo` は、ウィンドウ クラス情報を管理します。  3 種類のマクロ、`DECLARE_WND_CLASS`、`DECLARE_WND_CLASS_EX`、次の表に示すように `DECLARE_WND_SUPERCLASS`の 1 によって通常、`CWndClassInfo` を使用します:  
  
|マクロ|説明|  
|---------|--------|  
|[DECLARE\_WND\_CLASS](../Topic/DECLARE_WND_CLASS.md)|新しいウィンドウ クラスの`CWndClassInfo` の登録情報。|  
|[DECLARE\_WND\_CLASS\_EX](../Topic/DECLARE_WND_CLASS_EX.md)|パラメーター クラスを含む新しいウィンドウ クラスの`CWndClassInfo` の登録情報。|  
|[DECLARE\_WND\_SUPERCLASS](../Topic/DECLARE_WND_SUPERCLASS.md)|既存のクラスに基づいていますが、を使用してウィンドウ クラスの`CWndClassInfo` の登録情報は別のウィンドウ プロシージャが。  この方法は superclassing 呼び出されます。|  
  
 既定では、[CWindowImpl](../Topic/CWindowImpl%20Class.md) は新しいウィンドウ クラスに基づいてウィンドウを作成するに `DECLARE_WND_CLASS` のマクロが含まれています。  DECLARE\_WND\_CLASS は、コントロールの既定のスタイルと背景色を提供します。  独自のスタイルと背景色を指定する場合は、クラスを `CWindowImpl` から派生し、クラス定義に `DECLARE_WND_CLASS_EX` のマクロを含めます。  
  
 既存のウィンドウ クラスに基づいてペインを作成するには、クラスを `CWindowImpl` から派生し、クラス定義に `DECLARE_WND_SUPERCLASS` のマクロを含めます。  以下はその例です。  
  
 [!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/CPP/cwndclassinfo-class_1.h)]  
  
 ウィンドウ クラスの詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [ウィンドウ クラス](http://msdn.microsoft.com/library/windows/desktop/ms632596) を参照してください。  
  
 ATL でウィンドウを使用する方法の詳細については、" " [ATL ウィンドウ クラス](../Topic/ATL%20Window%20Classes.md)を参照してください。  
  
## 必要条件  
 **Header:** atlwin.h  
  
## 参照  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)