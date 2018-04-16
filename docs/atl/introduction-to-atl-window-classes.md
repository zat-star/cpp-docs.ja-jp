---
title: "ATL ウィンドウ クラスの概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- window classes
ms.assetid: 503efc2c-a269-495d-97cf-3fb300d52f3d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 636fe8aa87b6880f5cda77fb46fc481d99d78a81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="introduction-to-atl-window-classes"></a>ATL ウィンドウ クラスの概要
実装し、ウィンドウの操作は、次の ATL クラスが設計されています。  
  
-   [CWindow](../atl/reference/cwindow-class.md)するウィンドウ ハンドルをアタッチすることができます、`CWindow`オブジェクト。 呼び出して`CWindow`ウィンドウを操作するメソッド。  
  
-   [CWindowImpl](../atl/reference/cwindowimpl-class.md)新しいウィンドウを実装し、メッセージ マップでのメッセージを処理することができます。 作成ウィンドウでは、既存のウィンドウを新しい Windows クラス、スーパークラス、既存のクラスまたはサブクラスに基づいています。  
  
-   [CDialogImpl](../atl/reference/cdialogimpl-class.md)モーダルまたはモードレス ダイアログ ボックスとプロセス メッセージ メッセージ マップを実装することができます。  
  
-   [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md)構築済みクラスのメッセージ マップが含まれているウィンドウを別のクラスの実装です。 使用して`CContainedWindowT`1 つのクラスでのメッセージ処理を一元管理することができます。  
  
-   [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) ActiveX コントロールをホストするダイアログ ボックス (モーダルまたはモードレス) を実装することができます。  
  
-   [CSimpleDialog](../atl/reference/csimpledialog-class.md)基本的な機能を持つモーダル ダイアログ ボックスを実装することができます。  
  
-   [CAxWindow](../atl/reference/caxwindow-class.md) ActiveX コントロールをホストするウィンドウを実装することができます。  
  
-   [CAxWindow2T](../atl/reference/caxwindow2t-class.md)ライセンスされた ActiveX コントロールをホストするウィンドウを実装することができます。  
  
 特定のウィンドウ クラスに加えて、ATL は、ATL ウィンドウ オブジェクトの実装を容易にするために設計されたいくつかのクラスを提供します。 それらは次のとおりです。  
  
-   [CWndClassInfo](../atl/reference/cwndclassinfo-class.md)新しいウィンドウ クラスの情報を管理します。  
  
-   [CWinTraits](../atl/reference/cwintraits-class.md)と[CWinTraitsOR](../atl/reference/cwintraitsor-class.md) ATL ウィンドウ オブジェクトの特徴を標準化する単純なメソッドを提供します。  
  
## <a name="see-also"></a>参照  
 [ウィンドウ クラス](../atl/atl-window-classes.md)

