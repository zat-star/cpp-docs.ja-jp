---
title: "ツリー コントロールのドラッグ アンド ドロップ操作 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "CTreeCtrl クラス, ドラッグ アンド ドロップ操作"
  - "ドラッグ アンド ドロップ, CTreeCtrl"
  - "ツリー コントロール, ドラッグ アンド ドロップ操作"
ms.assetid: 3cf78b4c-4579-4fe1-9bc9-c5ab876e4af1
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ツリー コントロールのドラッグ アンド ドロップ操作
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ユーザーが項目のドラッグを開始すると、ツリー コントロール \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) は、通知を送信します。  コントロールは、ユーザーがマウスの右ボタンでのドラッグを開始すると、ユーザーがマウスの左ボタンと [TVN\_BEGINRDRAG](http://msdn.microsoft.com/library/windows/desktop/bb773509) 通知メッセージのアイテムのドラッグを開始すると [TVN\_BEGINDRAG](http://msdn.microsoft.com/library/windows/desktop/bb773504) 通知メッセージを送信します。  ツリー コントロールは、ツリー コントロールに **TVS\_DISABLEDRAGDROP** のスタイルを指定することにより、これらの通知を送信することを防ぐことができます。  
  
 [CreateDragImage](../Topic/CTreeCtrl::CreateDragImage.md) のメンバー関数を呼び出して、ドラッグ操作中に表示するイメージを取得します。  ツリー コントロールは、ドラッグした項目のラベルに基づいてドラッグ ビットマップを作成します。  ツリー コントロールは、イメージ リストを作成し、ビットマップを追加し、[CImageList](../Topic/CImageList%20Class.md) オブジェクトへのポインターを返します。  
  
 実際に項目をドラッグするコードを記述する必要があります。  通常は、ドラッグ操作が開始された後、イメージ リストの関数のドラッグ機能を使用し、送信 [WM\_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) と [WM\_LBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms645608) \(または [WM\_RBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms646243)\) メッセージを処理する必要があります。  イメージ リストの関数の詳細については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の *" MFC リファレンス"* の [CImageList](../Topic/CImageList%20Class.md) と [イメージ リスト](http://msdn.microsoft.com/library/windows/desktop/bb761389) を参照します。  ツリー ビュー コントロールのアイテムのドラッグに関する詳細については、[!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)]の [ツリー ビュー アイテムのドラッグ](http://msdn.microsoft.com/library/windows/desktop/bb760017)、または参照します。  
  
 ツリー コントロールの項目をドラッグ アンド ドロップ操作のターゲットである場合、マウス カーソルがターゲット項目にあることを確認する必要があります。  [HitTest](../Topic/CTreeCtrl::HitTest.md) のメンバー関数を呼び出すことによって確認できます。  マウス カーソルの現在の座標を含む [TVHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb773448) 構造体の点および整数、アドレスを指定します。  関数の戻り値は、整数または構造がツリー コントロールに対するマウス カーソルの位置を示すフラグが格納されます。  カーソルがツリー コントロール項目の場合、構造体は項目の処理も含まれます。  
  
 `TVIS_DROPHILITED` 値に状態を設定するために項目が [SetItem](../Topic/CTreeCtrl::SetItem.md) のメンバー関数を呼び出すことにより、ドラッグ アンド ドロップ操作のターゲットであることを示すことができます。  この状態がある項目はドラッグ アンド ドロップ ターゲットを示すために使用されるスタイルで描画されます。  
  
## 参照  
 [CTreeCtrl の使い方](../Topic/Using%20CTreeCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)