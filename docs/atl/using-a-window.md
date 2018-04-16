---
title: ウィンドウ (ATL) を使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ATL, windows
- CWindow class, about CWindow class
- windows [C++], ATL
ms.assetid: b3b9cc8e-4287-486b-b080-38852bc2943a
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a2be573e10190b385274de9afab498c77a094550
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-a-window"></a>ウィンドウを使用します。
クラス[CWindow](../atl/reference/cwindow-class.md)ウィンドウを使用することができます。 ウィンドウをアタッチすると、`CWindow`オブジェクトを呼び出すことができますし、`CWindow`ウィンドウを操作するメソッド。 `CWindow`含まれています、`HWND`に変換する演算子、`CWindow`オブジェクトを`HWND`です。 そのために渡すことができます、`CWindow`ウィンドウへのハンドルを必要とするすべての関数オブジェクト。 簡単に組み合わせることができます`CWindow`メソッド呼び出しと、一時オブジェクトを作成しなくても、Win32 関数の呼び出しです。  
  
 `CWindow`のみに 2 つのデータ メンバーを持ちます (ウィンドウ ハンドルと既定のサイズ)、コードのオーバーヘッドは必要ありません。 さらに、多くの`CWindow`メソッドは、単純に対応する Win32 API 関数をラップします。 使用して`CWindow`、`HWND`メンバーが自動的に Win32 関数に渡されます。  
  
 使用するだけでなく`CWindow`を直接ことができますもから派生したクラスにデータやコードを追加します。 ATL 自体から 3 つのクラスを派生する`CWindow`: [CWindowImpl](../atl/implementing-a-window.md)、 [CDialogImpl](../atl/implementing-a-dialog-box.md)、および[CContainedWindowT](../atl/using-contained-windows.md)です。  
  
## <a name="see-also"></a>参照  
 [ウィンドウ クラス](../atl/atl-window-classes.md)

