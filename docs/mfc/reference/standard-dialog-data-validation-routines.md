---
title: "標準的なダイアログ データ バリデーション ルーチン | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "標準ダイアログ, データ バリデーション ルーチン"
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
caps.latest.revision: 13
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 標準的なダイアログ データ バリデーション ルーチン
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックでは、MFC のコモン ダイアログ コントロールに使用される標準的なダイアログ データ バリデーション \(DDV\) ルーチンを紹介します。  
  
> [!NOTE]
>  標準的なダイアログ データ エクスチェンジ ルーチンはヘッダー ファイル afxdd\_.h に定義されています。  ただし、アプリケーションでは afxwin.h をインクルードするようにしてください。  
  
### DDV 関数  
  
|||  
|-|-|  
|[DDV\_MaxChars](../Topic/DDV_MaxChars.md)|特定のコントロールの値の文字数が、指定された最大値を超えていないかどうかを検証します。|  
|[DDV\_MinMaxByte](../Topic/DDV_MinMaxByte.md)|特定のコントロールの値が、指定された **BYTE** 範囲を超えていないかどうかを検証します。|  
|[DDV\_MinMaxDateTime](../Topic/DDV_MinMaxDateTime.md)|特定のコントロールの値が、指定された日時範囲を超えていないかどうかを検証します。|  
|[DDV\_MinMaxDouble](../Topic/DDV_MinMaxDouble.md)|特定のコントロールの値が、指定された **double** 範囲を超えていないかどうかを検証します。|  
|[DDV\_MinMaxDWord](../Topic/DDV_MinMaxDWord.md)|特定のコントロールの値が、指定された **DWORD** 範囲を超えていないかどうかを検証します。|  
|[DDV\_MinMaxFloat](../Topic/DDV_MinMaxFloat.md)|特定のコントロールの値が、指定された **float** 範囲を超えていないかどうかを検証します。|  
|[DDV\_MinMaxInt](../Topic/DDV_MinMaxInt.md)|特定のコントロールの値が、指定された **int** 範囲を超えていないかどうかを検証します。|  
|[DDV\_MinMaxLong](../Topic/DDV_MinMaxLong.md)|特定のコントロールの値が、指定された **long** 範囲を超えていないかどうかを検証します。|  
|[DDV\_MinMaxLongLong](../Topic/DDV_MinMaxLongLong.md)|特定のコントロールの値が、指定された **LONGLONG** 範囲を超えていないかどうかを検証します。|  
|[DDV\_MinMaxMonth](../Topic/DDV_MinMaxMonth.md)|特定のコントロールの値が、指定された日付範囲を超えていないかどうかを検証します。|  
|[DDV\_MinMaxShort](../Topic/DDV_MinMaxShort.md)|特定のコントロールの値が、指定された **short** 範囲を超えていないかどうかを検証します。|  
|[DDV\_MinMaxSlider](../Topic/DDV_MinMaxSlider.md)|特定のスライダー コントロールの値が、指定された範囲内にあるかどうかを検証します。|  
|[DDV\_MinMaxUInt](../Topic/DDV_MinMaxUInt.md)|特定のコントロールの値が、指定された **UINT** 範囲を超えていないかどうかを検証します。|  
|[DDV\_MinMaxULongLong](../Topic/DDV_MinMaxULongLong.md)|特定のコントロールの値が、指定された **ULONGLONG** 範囲を超えていないかどうかを検証します。|  
  
## 参照  
 [標準的なダイアログ データ エクスチェンジ ルーチン](../Topic/Standard%20Dialog%20Data%20Exchange%20Routines.md)   
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)