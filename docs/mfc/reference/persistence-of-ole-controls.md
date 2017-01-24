---
title: "OLE コントロールの永続化 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE コントロール, 永続化"
  - "永続化, OLE コントロール"
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
caps.latest.revision: 17
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE コントロールの永続化
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE コントロールの機能の 1 つに、プロパティの永続化 \(シリアル化\) があります。この機能を使用して、プロパティ値をファイルやストリームから読み出したり、ファイルやストリームに書き込んだりできます。  コンテナー アプリケーションはシリアル化を使用して、アプリケーションがコントロールを破棄した後でも、コントロールのプロパティ値を格納できます。  後でコントロールの新しいインスタンスが作成されたときに、OLE コントロールのプロパティ値をファイルまたはストリームから読み出せます。  
  
### OLE コントロールの永続化  
  
|||  
|-|-|  
|[PX\_Blob](../Topic/PX_Blob.md)|バイナリ ラージ オブジェクト \(BLOB: Binary Large Object\) データを格納するコントロール プロパティを交換します。|  
|[PX\_Bool](../Topic/PX_Bool.md)|**BOOL** 型のコントロール プロパティを交換します。|  
|[PX\_Color](../Topic/PX_Color.md)|コントロールのカラー プロパティを交換します。|  
|[PX\_Currency](../Topic/PX_Currency.md)|**CY** 型のコントロール プロパティを交換します。|  
|[PX\_DataPath](../Topic/PX_DataPath.md)|`CDataPathProperty` 型のコントロール プロパティを交換します。|  
|[PX\_Double](../Topic/PX_Double.md)|**double** 型のコントロール プロパティを交換します。|  
|[PX\_Font](../Topic/PX_Font.md)|コントロールのフォント プロパティを交換します。|  
|[PX\_Float](../Topic/PX_Float.md)|**float** 型のコントロール プロパティを交換します。|  
|[PX\_IUnknown](../Topic/PX_IUnknown.md)|未定義型のコントロール プロパティを交換します。|  
|[PX\_Long](../Topic/PX_Long.md)|**long** 型のコントロール プロパティを交換します。|  
|[PX\_Picture](../Topic/PX_Picture.md)|コントロールのピクチャ プロパティを交換します。|  
|[PX\_Short](../Topic/PX_Short.md)|**short** 型のコントロール プロパティを交換します。|  
|[PX\_ULong](../Topic/PX_ULong.md)|**ULONG** 型のコントロール プロパティを交換します。|  
|[PX\_UShort](../Topic/PX_UShort.md)|**USHORT** 型のコントロール プロパティを交換します。|  
|[PX\_String](../Topic/PX_String.md)|文字列コントロール プロパティを交換します。|  
|[PX\_VBXFontConvert](../Topic/PX_VBXFontConvert.md)|VBX コントロールのフォント関連プロパティを OLE コントロール フォント プロパティに交換します。|  
  
 また、指定した GUID が `TYPEDESC` と一致するかどうかを調べる `AfxOleTypeMatchGuid` グローバル関数が用意されています。  
  
## 参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)