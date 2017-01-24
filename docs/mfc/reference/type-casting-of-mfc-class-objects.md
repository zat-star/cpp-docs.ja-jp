---
title: "MFC クラス オブジェクトの型キャスト | Microsoft Docs"
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
  - "vc.mfc.macros.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "キャスト (型を)"
  - "マクロ, キャスト (ポインターを)"
  - "マクロ, 型キャスト"
  - "ポインター, 型キャスト"
  - "型キャスト"
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
caps.latest.revision: 15
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC クラス オブジェクトの型キャスト
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

型キャスト マクロは、指定されたポインターを特定のクラスのオブジェクトへのポインターにキャストします。キャスト時に、キャストが適正かどうかの確認を行うことも行わないこともできます。  
  
 MFC の型キャスト マクロの一覧表を、以下に示します。  
  
### MFC クラス オブジェクトへのポインターにキャストするマクロ  
  
|||  
|-|-|  
|[DYNAMIC\_DOWNCAST](../Topic/DYNAMIC_DOWNCAST.md)|キャストが適正なものかどうかを調べ、ポインターをクラス オブジェクトのポインターへキャストします。|  
|[STATIC\_DOWNCAST](../Topic/STATIC_DOWNCAST.md)|任意のクラスのオブジェクトへのポインターを、関連する型のポインターにキャストします。  デバッグ バージョンのビルドでは、オブジェクトが対象の型に含まれていないと、**ASSERT** が実行されます。|  
  
## 参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)