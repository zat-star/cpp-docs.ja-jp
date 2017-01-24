---
title: "永続化と初期化の最適化 | Microsoft Docs"
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
  - "MFC ActiveX コントロール, 最適化"
  - "最適化, ActiveX コントロール"
  - "最適化 (パフォーマンスの), ActiveX コントロール"
  - "パフォーマンス, ActiveX コントロール"
ms.assetid: e821e19e-b9eb-49ab-b719-0743420ba80b
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 永続化と初期化の最適化
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コントロールの既定で、永続性、および初期化は `DoPropExchange` のメンバー関数によって処理されます。  一般的なコントロールでは、この関数は **PX\_** のいくつかの関数 \(`PX_Color`、`PX_Font`など\) の呼び出しは、各プロパティの 1 が含まれます。  
  
 `DoPropExchange` の単一の実装を持つコンテナーで使用されるいわゆる「プロパティ バッグ」形式で初期化、永続化、永続化にバイナリ形式で使用できるこのにメリットがあります。  この 1 種類の関数が 1 の便利な場所のプロパティと既定値に関するすべての情報を提供します。  
  
 ただし、この一般性が効率を犠牲にしています。  **PX\_** 関数柔軟性を直接より大きい本来より効率的であり、あまり柔軟な方法で取得、多階層の実装。  また、コントロールが **PX\_** 関数に既定値を渡すと、その既定値は状況に既定値は必ずしも使用されない場合は、必ず指定する必要があります。  既定値を生成できることが重要なタスク値をアンビエント プロパティから取得した場合 \(たとえば、\) の場合、既定値が使用されていない場合は、追加の不要な処理が実行されます。  
  
 コントロールの `Serialize` 関数をオーバーライドすることにより、コントロールのバイナリ永続性パフォーマンスが向上します。  このメンバー関数の既定の実装は `DoPropExchange` 関数を呼び出します。  これをオーバーライドして、バイナリ永続性に直接実装を提供できます。  たとえば、`DoPropExchange` でこの関数を検討する:  
  
 [!code-cpp[NVC_MFC_AxOpt#1](../mfc/codesnippet/CPP/optimizing-persistence-and-initialization_1.cpp)]  
  
 次のようにこのコントロールのバイナリ永続性のパフォーマンスを向上させるには、`Serialize` の関数をオーバーライドするには:  
  
 [!code-cpp[NVC_MFC_AxOpt#2](../mfc/codesnippet/CPP/optimizing-persistence-and-initialization_2.cpp)]  
  
 `dwVersion` のローカル変数が読み込まれるまたは格納済みのコントロールの永続的な状態のバージョンを検出するために使用できます。  [CPropExchange::GetVersion](../Topic/CPropExchange::GetVersion.md)を呼び出す代わりに、変数を使用できます。  
  
 次のよう **BOOL** のプロパティの永続的な形式の小さい領域を節約するためには、それを `PX_Bool`で生成された形式との互換性を保つため\)、**BYTE**としてプロパティを格納し、:  
  
 [!code-cpp[NVC_MFC_AxOpt#3](../mfc/codesnippet/CPP/optimizing-persistence-and-initialization_3.cpp)]  
  
 ロードの場合で、テンポラリ変数に使用され、表示される値は **BYTE** の参照に割り当てられ `m_boolProp` ではなくをキャストします。  キャスト手法は残りのバイトを初期化前の状態に戻されてと `m_boolProp` を変更する 1 バイトだけで発生します。  
  
 同じコントロールでは、次のようにオーバーライドの [COleControl::OnResetState](../Topic/COleControl::OnResetState.md) でコントロールの初期化を最適化するには:  
  
 [!code-cpp[NVC_MFC_AxOpt#4](../mfc/codesnippet/CPP/optimizing-persistence-and-initialization_4.cpp)]  
  
 `Serialize` と `OnResetState` がオーバーライドされ、`DoPropExchange` 関数が、プロパティ バッグの形式で永続化に使用されるため、そのまま保持する必要があります。  これらの関数のコントロールが永続性機構に関係なくコンテナーを使用するプロパティを一貫して管理するように 3 つすべてを維持することが重要です。  
  
## 参照  
 [MFC ActiveX コントロール : 最適化](../mfc/mfc-activex-controls-optimization.md)