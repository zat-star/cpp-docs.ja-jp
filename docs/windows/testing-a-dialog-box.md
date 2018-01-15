---
title: "ダイアログ ボックスのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Test Dialog command
- testing, dialog boxes
- dialog boxes, testing
ms.assetid: 45034ee9-c554-4f4b-8c46-6ddefdee8951
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d81d288453e56acfb02a123075692b907d371578
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="testing-a-dialog-box"></a>ダイアログ ボックスのテスト
ダイアログ ボックスを設計する際には、プログラムをコンパイルせずに実行時の動作をシミュレートし、テストできます。 このモードでは、次を行うことができます。  
  
-   テキストの入力、コンボ ボックスの一覧での選択、オプションのオンとオフの切り替え、コマンドの選択。  
  
-   タブ オーダーのテスト。  
  
-   オプション ボタンやチェック ボックスなど、コントロールのグループ化のテスト。  
  
-   ダイアログ ボックスにあるコントロールのキーボード ショートカットのテスト。  
  
    > [!NOTE]
    >  ウィザードを使用したダイアログ ボックスのコードへの接続は、シミュレーションに含まれません。  
  
 通常、テストするダイアログ ボックスはメイン プログラム ウィンドウの相対位置に表示されます。 ダイアログ ボックスの [Absolute Align] を [True] に設定している場合、ダイアログ ボックスは画面の左上隅の相対位置に表示されます。  
  
### <a name="to-test-a-dialog-box"></a>ダイアログ ボックスをテストするには  
  
1.  ダイアログ エディターがアクティブなウィンドウである場合は、メニュー バーの **[書式]**、 **[ダイアログのテスト]**をクリックします。  
  
2.  シミュレーションを終了するには、Esc キーを押すか、またはテストしているダイアログ ボックスの **[閉じる]** をクリックします。  
  
 マネージ プロジェクトにリソースを追加する方法については、次を参照してください。[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)です。  
  
 必要条件  
  
 Win32  
  
## <a name="see-also"></a>参照  
 [ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)   
 [ダイアログ エディター](../windows/dialog-editor.md)   
 [[ダイアログ エディター] ツール バーの表示と非表示](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)

