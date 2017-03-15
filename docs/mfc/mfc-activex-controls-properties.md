---
title: "MFC ActiveX コントロール : プロパティ | Microsoft Docs"
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
  - "MFC ActiveX コントロール, プロパティ"
  - "プロパティ [MFC]"
  - "プロパティ [MFC], ActiveX コントロール"
ms.assetid: b678a53c-0d9e-476f-8aa0-23b80baaba46
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# MFC ActiveX コントロール : プロパティ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ActiveX コントロールは、コンテナーと通信するためにイベントを発生させます。  コンテナーは、戻り値として、コントロールと通信するためにメソッドとプロパティを使用します。  メソッドとプロパティは、類似の使用中に、メンバー関数、それぞれ、想定し、C\+\+. C\+\+ メンバー変数が用意されています。  プロパティはどのコンテナーに公開されている ActiveX コントロールのデータ メンバーです。  プロパティは、ActiveX コントロールを含むオートメーション クライアントと ActiveX コントロール コンテナーなどのアプリケーションへのインターフェイスを提供します。  
  
 プロパティは、属性と呼ばれます。  
  
 ActiveX コントロール メソッドの詳細については、記事 [MFC ActiveX コントロール: メソッド](../mfc/mfc-activex-controls-methods.md)を参照します。  
  
 ActiveX コントロールは、ストック イベントとカスタム メソッドやカスタム プロパティ実装できます。  クラス `COleControl`、ストック プロパティに実装を提供します。\(ストック プロパティの完全な一覧については、[MFC ActiveX コントロール: ストック プロパティの追加](../Topic/MFC%20ActiveX%20Controls:%20Adding%20Stock%20Properties.md)を参照してください\)。開発者が定義したカスタム プロパティは ActiveX コントロールに特殊な機能を追加します。  詳細については、「[MFC ActiveX コントロール: カスタム プロパティの追加](../mfc/mfc-activex-controls-adding-custom-properties.md)」を参照してください。  
  
 カスタムとストック プロパティはいずれも、メソッドなどのプロパティを処理し、`COleControl` のメソッドと既存のメンバー関数を使用してディスパッチ マップで構成される機能がサポートされます。  また、これらのプロパティは、開発者がコントロールに情報を渡すために使用するパラメーターを使用できます。  
  
 次のトピックでは、ActiveX コントロール プロパティについて詳細に説明します。:  
  
-   [MFC ActiveX コントロール: ストック プロパティの追加](../Topic/MFC%20ActiveX%20Controls:%20Adding%20Stock%20Properties.md)  
  
-   [MFC ActiveX コントロール: カスタム プロパティの追加](../mfc/mfc-activex-controls-adding-custom-properties.md)  
  
-   [MFC ActiveX コントロール: 詳細プロパティの実装](../mfc/mfc-activex-controls-advanced-property-implementation.md)  
  
-   [MFC ActiveX コントロール: アクセスのアンビエント プロパティ](../mfc/mfc-activex-controls-accessing-ambient-properties.md)  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)