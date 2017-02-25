---
title: "ディスパッチ マップ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.maps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ディスパッチ マップ マクロ"
  - "ディスパッチ マップ"
  - "ディスパッチ マップ マクロ"
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# ディスパッチ マップ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE オートメーションには、メソッドを呼び出し、アプリケーション間でプロパティにアクセスする方法が用意されています。  Microsoft Foundation Class ライブラリには、このような要求をディスパッチするための機構 "ディスパッチ マップ" があります。ディスパッチ マップは、オブジェクト関数とプロパティの内部名および外部名、およびプロパティ自体のデータ型と関数引数のデータ型を示します。  
  
### ディスパッチ マップ  
  
|||  
|-|-|  
|[DECLARE\_DISPATCH\_MAP](../Topic/DECLARE_DISPATCH_MAP.md)|ディスパッチ マップを使用してクラスのメソッドとプロパティを公開することを宣言します。クラスの宣言の中で使用する必要があります。|  
|[BEGIN\_DISPATCH\_MAP](../Topic/BEGIN_DISPATCH_MAP.md)|ディスパッチ マップの定義を開始します。|  
|[END\_DISPATCH\_MAP](../Topic/END_DISPATCH_MAP.md)|ディスパッチ マップの定義を終了します。|  
|[DISP\_FUNCTION](../Topic/DISP_FUNCTION.md)|ディスパッチ マップで使用して、OLE オートメーション関数を定義します。|  
|[DISP\_PROPERTY](../Topic/DISP_PROPERTY.md)|OLE オートメーションのプロパティを定義します。|  
|[DISP\_PROPERTY\_EX](../Topic/DISP_PROPERTY_EX.md)|OLE オートメーション プロパティを定義し、Get 関数と Set 関数を指定します。|  
|[DISP\_PROPERTY\_NOTIFY](../Topic/DISP_PROPERTY_NOTIFY.md)|通知機能付きの OLE オートメーション プロパティを定義します。|  
|[DISP\_PROPERTY\_PARAM](../Topic/DISP_PROPERTY_PARAM.md)|パラメーターをとる OLE オートメーション プロパティを定義し、**Get** 関数と `Set` 関数を指定します。|  
|[DISP\_DEFVALUE](../Topic/DISP_DEFVALUE.md)|既存のプロパティをオブジェクトの既定値にします。|  
  
## 参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)