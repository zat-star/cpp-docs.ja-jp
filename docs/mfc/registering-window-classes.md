---
title: "ウィンドウ クラスの登録 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WndProc
dev_langs:
- C++
helpviewer_keywords:
- window classes [MFC], registering
- registry [MFC], registering classes
- AfxRegisterWndClass method [MFC]
- MFC, windows
- WinMain method [MFC], and registering window classes
- WndProc method [MFC]
- classes [MFC], registering window classes
- WinMain method [MFC]
- registering window classes [MFC]
ms.assetid: 30994bc4-a362-43da-bcc5-1bf67a3fc929
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 92f5673aac014abdd4fd19425d9ae849f64284ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="registering-window-classes"></a>ウィンドウ クラスの登録
Windows の従来のプログラミングでは"ウィンドウ"クラスは、windows の任意の数を作成できるから「クラス」(C++ クラスではなく) の特性を定義します。 この種類のクラスは、テンプレート、または windows を作成するためのモデルです。  
  
## <a name="window-class-registration-in-traditional-programs-for-windows"></a>Windows 用の従来のプログラムでウィンドウ クラスの登録  
 Windows で MFC を使用しない従来のプログラムでの「ウィンドウ プロシージャ」で、ウィンドウにすべてのメッセージを処理するか、"**WndProc**"。 A **WndProc** 「ウィンドウ クラスの登録」プロセスを使用してウィンドウに関連付けられています。 メイン ウィンドウが登録されている、`WinMain`関数が windows の他のクラスは、アプリケーションで任意の場所登録できます。 登録にへのポインターを格納する構造体は、 **WndProc**カーソル、背景のブラシの仕様と機能などです。 呼び出す前に、クラスの文字列名と共に、パラメーターとして構造体が渡される、 **RegisterClass**関数。 したがって、登録クラスは、複数のウィンドウで共有できます。  
  
## <a name="window-class-registration-in-mfc-programs"></a>MFC プログラムでウィンドウ クラスの登録  
 これに対し、ほとんどのウィンドウ クラスの登録アクティビティは、MFC フレームワーク プログラムで自動的に行われます。 MFC を使用している場合は、通常クラス継承の標準の C++ 構文を使用して既存のライブラリ クラスから C++ ウィンドウ クラスを派生します。 フレームワークはまだ使用従来「登録クラス」とは、必要なときに登録されているいくつかの標準的なものを提供します。 呼び出して追加登録クラスを登録することができます、 [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass)グローバル関数とに登録されているクラスを渡す、**作成**のメンバー関数`CWnd`です。 ここでは、従来の説明に従って Windows の「登録クラス」は、C++ のクラスと混同しないでください。  
  
 詳細については、次を参照してください。[テクニカル ノート 1:](../mfc/tn001-window-class-registration.md)です。  
  
## <a name="see-also"></a>参照  
 [ウィンドウの作成](../mfc/creating-windows.md)

