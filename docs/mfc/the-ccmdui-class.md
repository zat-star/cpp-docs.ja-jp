---
title: "CCmdUI クラス | Microsoft Docs"
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
  - "CCmdUI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCmdUI クラス, メニュー更新"
  - "ツール バー [C++], 更新"
  - "更新ハンドラー"
  - "更新 (ユーザー インターフェイス オブジェクトを)"
  - "ユーザー インターフェイス オブジェクト, 更新"
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCmdUI クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これがハンドラーに更新コマンドをルーティングすると、フレームワークは `CCmdUI` オブジェクトにハンドラーへのポインターを渡します \(または `CCmdUI`オブジェクト\-派生クラス\)。  このオブジェクトは、コマンドを生成したメニュー項目やツール バー ボタンや他のユーザー インターフェイス オブジェクトを表します。  更新ハンドラーはポインターを通じてユーザー インターフェイス オブジェクトを更新するに `CCmdUI` 構造体のメンバー関数を呼び出します。  たとえば、Clear の更新ハンドラーは、すべてのメニュー項目の次に示します:  
  
 [!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/CPP/the-ccmdui-class_1.cpp)]  
  
 このハンドラーは、メニュー項目へのアクセスを持つオブジェクトの **有効化** メンバー関数を呼び出します。  **有効化** は 項目を使用できるようになります。  
  
## 参照  
 [ユーザー インターフェイス オブジェクトの更新方法](../mfc/how-to-update-user-interface-objects.md)