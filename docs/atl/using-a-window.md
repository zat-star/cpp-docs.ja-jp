---
title: "ウィンドウの使い方 | Microsoft Docs"
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
  - "ATL, ウィンドウ"
  - "CWindow クラス, CWindow クラスの概要"
  - "ウィンドウ [C++], ATL"
ms.assetid: b3b9cc8e-4287-486b-b080-38852bc2943a
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ウィンドウの使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラス [CWindow](../atl/reference/cwindow-class.md) は、ウィンドウを使用することができます。  `CWindow` のウィンドウをオブジェクトにアタッチして、ウィンドウを操作するために `CWindow` のメソッドを呼び出します。  `CWindow` は、`HWND`への `CWindow` のオブジェクトを変換するに `HWND` の演算子が用意されています。  したがって、ウィンドウへのハンドルを必要とするすべての関数への `CWindow` のオブジェクトを渡すこともできます。  一時的なオブジェクトを作成せずに簡単に `CWindow` のメソッドの呼び出しや Win32 関数を呼び出し、混在させることができます。  
  
 `CWindow` に 2 だけデータ メンバー \(ウィンドウ ハンドルと既定のサイズ\) であるため、コードのオーバーヘッドを課しません。  また、`CWindow` のメソッドの多くは、対応する Win32 API 関数をラップします。  `CWindow`を使用して、`HWND` のメンバーは、Win32 関数に自動的に渡されます。  
  
 `CWindow` を直接使用することに加えて、データかのクラスにコードを追加するには、アプリケーションから取得できます。  ATL 自体は `CWindow`~ 3 個のクラスを取得します: [CWindowImpl](../atl/implementing-a-window.md)、[CDialogImpl](../atl/implementing-a-dialog-box.md)と [CContainedWindowT](../Topic/Using%20Contained%20Windows.md)。  
  
## 参照  
 [ウィンドウ クラス](../Topic/ATL%20Window%20Classes.md)