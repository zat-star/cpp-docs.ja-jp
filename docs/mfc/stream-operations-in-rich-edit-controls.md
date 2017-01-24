---
title: "リッチ エディット コントロールでのストリーム操作 | Microsoft Docs"
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
  - "CRichEditCtrl クラス, ストリーム操作"
  - "CRichEditCtrl クラス, ストリーム ストレージ"
  - "リッチ エディット コントロール, ストリーム操作"
  - "ストレージ, ストリーム (CRichEditCtrl の)"
  - "ストリーム操作 (CRichEditCtrl での)"
  - "ストリーム ストレージと CRichEditCtrl"
ms.assetid: 110b4684-1e76-4ca6-9ef0-5bc8b2d93c78
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# リッチ エディット コントロールでのストリーム操作
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リッチ エディット コントロール \([CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)\) またはからデータを転送するストリームを使用できます。  ストリームは、バッファーをアプリケーション定義されたコールバック関数を指定する [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) 構造体によって定義されます。  
  
 リッチ エディット コントロールにデータを読み込むには、つまりデータをストリームなど\)、[StreamIn](../Topic/CRichEditCtrl::StreamIn.md) メンバー関数を使用します。  コントロールが繰り返しバッファーにデータの一部を常に転送するアプリケーション定義されたコールバック関数が呼び出されます。  
  
 リッチ エディット コントロールの内容を保存するには \(つまり、データをストリームなど\)、[StreamOut](../Topic/CRichEditCtrl::StreamOut.md) メンバー関数を使用できます。  コントロールはバッファーを繰り返し記述し、アプリケーション定義のコールバック関数が呼び出されます。  各呼び出しの場合は、コールバック関数では、バッファーの内容を保存します。  
  
## 参照  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)