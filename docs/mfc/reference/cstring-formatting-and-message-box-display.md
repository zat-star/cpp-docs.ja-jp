---
title: "CString の書式指定とメッセージ ボックスの表示 | Microsoft Docs"
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
  - "vc.mfc.macros.strings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CString オブジェクト, 書式指定とメッセージ ボックス"
ms.assetid: d1068cf4-9cc5-4952-b9e7-d612c53cbc28
caps.latest.revision: 14
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CString の書式指定とメッセージ ボックスの表示
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

一部の関数は `CString` オブジェクトの書式を設定し、解析するために使用されます。  `CString` オブジェクトを処理するのがメッセージ ボックスに表示するテキストの書式指定文字列に適していますときはいつでも、これらの関数を使用できます。  
  
 関数のグループはメッセージ ボックスの表示のグローバル ルーチンが含まれます。  
  
### CString のメンバー関数  
  
|||  
|-|-|  
|[AfxExtractSubString](../Topic/AfxExtractSubString.md)|単一の文字で区切られている特定のソース文字列から部分文字列を抽出します。|  
|[AfxFormatString1](../Topic/AfxFormatString1.md)|書式指定文字列「ストリング テーブルに含まれる文字列の %1 "指定された文字列に置換されます。|  
|[AfxFormatString2](../Topic/AfxFormatString2.md)|ストリング テーブルに含まれる文字列の書式指定文字「%1 "や「%2 "の代替 2 桁の文字列。|  
|[AfxMessageBox](../Topic/AfxMessageBox.md)|メッセージ ボックスを表示します。|  
  
## 参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)   
 [CStringT クラス](../../atl-mfc-shared/reference/cstringt-class.md)