---
title: "MFC モジュールの状態データを管理する |Microsoft ドキュメント"
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
- global state [MFC]
- data management [MFC], MFC modules
- window procedure entry points [MFC]
- exported interfaces and global state [MFC]
- module states [MFC], saving and restoring
- data management [MFC]
- MFC, managing state data
- multiple modules [MFC]
- module state restored [MFC]
ms.assetid: 81889c11-0101-4a66-ab3c-f81cf199e1bb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2d070bb91d9c1c229feaa563123c12702a7b5027
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="managing-the-state-data-of-mfc-modules"></a>MFC モジュールの状態データの管理
この記事では、MFC のモジュールと (パス コードは、アプリケーションの実行時に) 実行のフロー モジュールに出入りする場合にこの状態を更新する方法の状態データについて説明します。 モジュールの状態を切り替える、`AFX_MANAGE_STATE`と`METHOD_PROLOGUE`マクロについても説明します。  
  
> [!NOTE]
>  「モジュール」とは、実行可能プログラムまたは DLL (または一連の Dll) に、アプリケーションの残りの部分に関係なく動作するが共有 MFC DLL のコピーを使用します。 ActiveX コントロールでは、モジュールの典型的な例を示します。  
  
 次の図に示すように、MFC では、アプリケーションで使用される各モジュールの状態データ。 このデータの例として、Windows のインスタンス ハンドル (リソースの読み込みに使用)、現在へのポインター`CWinApp`と`CWinThread`アプリケーション、OLE モジュール参照の数との間の接続を維持するマップのさまざまなオブジェクトWindows は、ハンドルと対応するオブジェクトのインスタンスの MFC オブジェクトです。 ただし、アプリケーションでは、複数のモジュールを使用するときに各モジュールの状態データはアプリケーション全体です。 代わりに、各モジュールには、MFC の状態データの独自のコピーがいます。  
  
 ![状態データの 1 つのモジュール &#40;アプリケーション&#41;] (../mfc/media/vc387n1.gif "vc387n1")  
単一モジュール (アプリケーション) の状態データ  
  
 モジュールの状態データは、構造体に含まれ、その構造体へのポインター経由で使用可能では常にします。 実行のフロー入力すると、特定のモジュールでは、次の図に示すようにそのモジュールの状態は、「現在」または「有効」状態にする必要があります。 したがって、各スレッド オブジェクトでは、そのアプリケーションの有効な状態の構造体へのポインターがあります。 このポインターがすべての更新を維持する時間が、アプリケーションのグローバル状態を管理して、各モジュールの状態の整合性の維持にとって重要です。 グローバル状態を正しく管理は、予期しないアプリケーションの動作をする可能性があります。  
  
 ![複数モジュールのデータを状態](../mfc/media/vc387n2.gif "vc387n2")  
複数モジュールの状態データ  
  
 つまり、各モジュールは、すべてのエントリ ポイントにあるモジュールの状態を正しく切り替えます。 「エントリ ポイント」とは、実行のフローがモジュールのコードを入力する場所の任意の場所です。 エントリ ポイントは、次のとおりです。  
  
-   [DLL のエクスポート関数](../mfc/exported-dll-function-entry-points.md)  
  
-   [COM インターフェイスのメンバー関数](../mfc/com-interface-entry-points.md)  
  
-   [ウィンドウ プロシージャ](../mfc/window-procedure-entry-points.md)  
  
## <a name="see-also"></a>参照  
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)

