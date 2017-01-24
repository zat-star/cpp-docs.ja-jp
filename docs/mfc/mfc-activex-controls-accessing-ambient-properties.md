---
title: "MFC ActiveX コントロール : アンビエント プロパティへのアクセス | Microsoft Docs"
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
  - "MFC ActiveX コントロール, アクセス (アンビエント プロパティに)"
  - "プロパティ [MFC], アクセス (アンビエントに)"
ms.assetid: fdc9db29-e6b0-45d2-a879-8bd60e2058a7
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC ActiveX コントロール : アンビエント プロパティへのアクセス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、ActiveX コントロールをコントロール コンテナーのアンビエント プロパティにアクセスする方法について説明します。  
  
 コントロールがコンテナーのアンビエント プロパティにアクセスすると、コンテナーに関する情報を取得できます。  これらのプロパティはコンテナーがユーザー モードまたはデザイナー モードになっているかどうかをコンテナーの背景色、コンテナー、および運用特性を使用して、現在のフォントなどの視覚的特性を、次のように公開します。  コントロールがコンテナーに埋め込まれている特定の外観と動作をするためにアンビエント プロパティを使用できます。  ただし、コントロールは、コンテナーが特定のアンビエント プロパティをサポートすることを想定する必要があります。  実際、コンテナーはアンビエント プロパティをまったくサポートされない場合があります。  アンビエント プロパティがない場合、コントロールは、適切な既定値を想定する必要があります。  
  
 アンビエント プロパティにアクセスするには、[COleControl::GetAmbientProperty](../Topic/COleControl::GetAmbientProperty.md)に呼び出しを行ってください。  この関数は、最初のパラメーターとしてアンビエント プロパティのディスパッチ ID を要求します \(ファイル OLECTL.H はアンビエント プロパティの標準セットのディスパッチ ID を定義します\)。  
  
 `GetAmbientProperty` 関数のパラメーターは、ディスパッチ ID、値を返す必要があるメモリが予測されるプロパティ型、ポインターを表示する複数のタグです。  このポインターを参照するデータの種類が異なるタグによって異なります。  関数の戻り値 **TRUE** コンテナー サポート プロパティ、それ以外の場合は **FALSE**を返します。  
  
 次のコード例 Get 「UserMode 呼び出されるアンビエント プロパティの値を」とプロパティがコンテナーでサポートされていない場合、**TRUE** の既定値と見なされます:  
  
 [!code-cpp[NVC_MFC_AxUI#30](../mfc/codesnippet/CPP/mfc-activex-controls-accessing-ambient-properties_1.cpp)]  
  
 利便性のために、`COleControl` はプロパティが使用できない場合によく使用されるアンビエント プロパティの多くは、およびメッセージの適切な既定値にアクセスするヘルパー関数を指定します。  これらのヘルパー関数は次のとおりです。:  
  
-   [COleControl::AmbientBackColor](../Topic/COleControl::AmbientBackColor.md)  
  
-   [AmbientDisplayName](../Topic/COleControl::AmbientDisplayName.md)  
  
-   [AmbientFont](../Topic/COleControl::AmbientFont.md)  
  
    > [!NOTE]
    >  呼び出し元に返されるフォントの **Release\( \)** を呼び出す必要があります。  
  
-   [AmbientForeColor](../Topic/COleControl::AmbientForeColor.md)  
  
-   [AmbientLocaleID](../Topic/COleControl::AmbientLocaleID.md)  
  
-   [AmbientScaleUnits](../Topic/COleControl::AmbientScaleUnits.md)  
  
-   [AmbientTextAlign](../Topic/COleControl::AmbientTextAlign.md)  
  
-   [AmbientUserMode](../Topic/COleControl::AmbientUserMode.md)  
  
-   [AmbientUIDead](../Topic/COleControl::AmbientUIDead.md)  
  
-   [AmbientShowHatching](../Topic/COleControl::AmbientShowHatching.md)  
  
-   [AmbientShowGrabHandles](../Topic/COleControl::AmbientShowGrabHandles.md)  
  
 アンビエント プロパティの値 \(コンテナーの操作によって変更されると、コントロールの **OnAmbientPropertyChanged** のメンバー関数が呼び出されます。  このような通知を処理するには、このメンバー関数をオーバーライドします。  **OnAmbientPropertyChanged** のパラメーターは影響を受けるアンビエント プロパティのディスパッチ ID です。  説明する一つ以上のアンビエント プロパティは変更されますが、情報プロパティが影響を受けていることをディスパッチ ID の値は **DISPID\_UNKNOWN**にあります。使用できません。  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)