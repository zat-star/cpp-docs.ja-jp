---
title: "Windows のサポート クラス (ATL) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.atl.windows
dev_langs:
- C++
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
ms.assetid: 750b14d5-d787-4d2b-9728-ac199ccad489
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b64654f0f483ec401b379ec4c512489ce8cac823
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="windows-support-classes"></a>Windows のサポート クラス
次のクラスは、windows をサポートを提供します。  
  
-   [_U_MENUorID](../atl/reference/u-menuorid-class.md)用のラッパーを提供**CreateWindow**と**について**です。  
  
-   [CWindow](../atl/reference/cwindow-class.md)ウィンドウを操作するためのメソッドが含まれています。 `CWindow` は、`CWindowImpl`、`CDialogImpl`、および `CContainedWindow` の基本クラスです。  
  
-   [CWindowImpl](../atl/reference/cwindowimpl-class.md)新しいウィンドウ クラスに基づくウィンドウを実装します。 こともできますサブクラスまたはスーパークラス ウィンドウです。  
  
-   [CDialogImpl](../atl/reference/cdialogimpl-class.md)  ダイアログ ボックスを実装します。  
  
-   [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) ActiveX コントロールをホストするダイアログ ボックス (モーダルまたはモードレス) を実装します。  
  
-   [CSimpleDialog](../atl/reference/csimpledialog-class.md)基本的な機能を持つ ダイアログ ボックス (モーダルまたはモードレス) を実装します。  
  
-   [CAxWindow](../atl/reference/caxwindow-class.md) ActiveX コントロールをホストするウィンドウを操作します。  
  
-   [CAxWindow2T](../atl/reference/caxwindow2t-class.md) ActiveX コントロールをホストし、ライセンスされた ActiveX コントロールをホストするためのサポートがウィンドウを操作するためのメソッドを提供します。  
  
-   [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md)別のオブジェクト内に含まれるウィンドウを実装します。  
  
-   [CWndClassInfo](../atl/reference/cwndclassinfo-class.md)新しいウィンドウ クラスの情報を管理します。  
  
-   [CDynamicChain](../atl/reference/cdynamicchain-class.md)メッセージ マップの動的な組み合わせをサポートしています。  
  
-   [CMessageMap](../atl/reference/cmessagemap-class.md)にそのメッセージを公開するオブジェクトが他のオブジェクトに対応付けが可能になります。  
  
-   [CWinTraits](../atl/reference/cwintraits-class.md) ATL ウィンドウ オブジェクトの特徴を標準化する単純なメソッドを提供します。  
  
-   [CWinTraitsOR](../atl/reference/cwintraitsor-class.md)ウィンドウ スタイルとウィンドウを作成するために使用する拡張スタイルの既定値を提供します。 ウィンドウの作成時に提供される値に、論理 OR 演算子を使用してこれらの値が追加されます。  
  
## <a name="related-articles"></a>関連トピック  
 [ATL ウィンドウ クラス](../atl/atl-window-classes.md)  
  
 [ATL チュートリアル](../atl/active-template-library-atl-tutorial.md)  
  
## <a name="see-also"></a>参照  
 [クラスの概要](../atl/atl-class-overview.md)   
 [メッセージ マップ マクロ](../atl/reference/message-map-macros-atl.md)   
 [Windows クラスに関するマクロ](../atl/reference/window-class-macros.md)

