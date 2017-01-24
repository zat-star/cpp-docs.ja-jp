---
title: "MFC ActiveX コントロール : メソッドからのエラー コードのリターン | Microsoft Docs"
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
  - "エラー [C++], ActiveX コントロール エラー コード"
  - "FireError メソッド"
  - "GetNotSupported メソッド"
  - "MFC ActiveX コントロール, エラー コード"
  - "SCODE, MFC ActiveX コントロール"
  - "SetNotSupported メソッド, 使用"
  - "ThrowError メソッド"
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC ActiveX コントロール : メソッドからのエラー コードのリターン
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、ActiveX コントロール メソッドからエラー コードを返す方法を説明します。  
  
 メソッド内でエラーが発生したことを示すには、パラメーターとして `SCODE` \(ステータス コード\) を受け取る [COleControl::ThrowError](../Topic/COleControl::ThrowError.md) メンバー関数を使用する必要があります。  定義済みのな `SCODE` を使用するか、独自の 1 を定義できます。  
  
> [!NOTE]
>  `ThrowError` Get または Set 関数またはオートメーション メソッド内部プロパティからエラーを返すための手段としてのみ使用されるようになっています。  これらは適切な例外ハンドラーがスタックにいる唯一の場合です。  
  
 ヘルパー関数は、[COleControl::SetNotSupported](../Topic/COleControl::SetNotSupported.md)[COleControl::GetNotSupported](../Topic/COleControl::GetNotSupported.md)と [COleControl::SetNotPermitted](../Topic/COleControl::SetNotPermitted.md)などの一般的な定義済みのな `SCODE`s 用にあります。  
  
 カスタム `SCODE`s の定義の定義済みのな `SCODE`s と説明の一覧については、ActiveX コントロールのセクションを参照してください [ActiveX コントロールの Handling Errors](../mfc/mfc-activex-controls-advanced-topics.md) : 高度なトピック。  
  
 コードの他の領域のレポートの例外の詳細については、ActiveX コントロールの [COleControl::FireError](../Topic/COleControl::FireError.md) とセクション [ActiveX コントロールの Handling Errors](../mfc/mfc-activex-controls-advanced-topics.md) を参照します: 高度なトピック。  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)