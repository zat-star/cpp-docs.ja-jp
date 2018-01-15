---
title: "C++ ウィンドウ オブジェクトと HWND の関係 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: HWND
dev_langs: C++
helpviewer_keywords:
- Windows window [MFC]
- window objects [MFC], HWND and
- HWND [MFC]
- CWnd class [MFC], HWND
- HWND, window objects [MFC]
ms.assetid: f2e76340-6691-4ee6-9424-0345634a9469
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b441077de3a81de569627b6d7acf7cee8ca17b33
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>C++ ウィンドウ オブジェクトと HWND の関係
ウィンドウ*オブジェクト*の C++ オブジェクトである`CWnd`クラス (または派生クラス)、プログラムを直接作成します。 プログラムのコンス トラクターとデストラクターの呼び出しに対する応答にします。 Windows*ウィンドウ*、不透明ハンドルをウィンドウに対応し、存在する場合、システム リソースを消費する、Windows 内部データ構造には、その一方で、します。 Windows のウィンドウは、「ウィンドウ ハンドル」によって識別される (`HWND`) 後に作成し、`CWnd`オブジェクトへの呼び出しによって作成されて、**作成**クラスのメンバー関数`CWnd`です。 プログラムの呼び出しまたはユーザーの操作のいずれか、ウィンドウを破壊する可能性があります。 ウィンドウ オブジェクトに使用するウィンドウ ハンドルが格納されている`m_hWnd`メンバー変数。 次の図は、C++ ウィンドウ オブジェクトと、Windows の期間の関係を示しています。 ウィンドウの作成は、後ほど[ウィンドウの作成](../mfc/creating-windows.md)です。 ウィンドウの破棄は、後ほど[ウィンドウ オブジェクトの破棄](../mfc/destroying-window-objects.md)です。  
  
 ![CWnd ウィンドウ オブジェクトと表示されるウィンドウ](../mfc/media/vc37fj1.gif "vc37fj1")  
ウィンドウ オブジェクトと Windows のウィンドウ  
  
## <a name="see-also"></a>参照  
 [Window オブジェクト](../mfc/window-objects.md)

