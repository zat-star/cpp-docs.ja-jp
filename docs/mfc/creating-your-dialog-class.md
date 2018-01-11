---
title: "ダイアログ クラスの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- files [MFC], creating
- dialog classes [MFC], Add Class Wizard
- dialog classes [MFC], creating
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f2d8d62dc21aacb29f1133596c7f04251e88f1b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="creating-your-dialog-class"></a>ダイアログ クラスの作成
各 ダイアログ ボックスに、プログラムでは、ダイアログ リソースを使用する新しいダイアログ クラスを作成します。  
  
 [クラスの追加](../ide/adding-a-class-visual-cpp.md)新しいダイアログ クラスを作成する方法について説明します。 次の項目はそのクラスの追加ウィザードとダイアログ クラスを作成するときに、します。H とします。指定された CPP ファイル:  
  
 の。H ファイル:  
  
-   ダイアログ クラスのクラス宣言します。 派生したクラスが[CDialog](../mfc/reference/cdialog-class.md)です。  
  
 の。CPP ファイル:  
  
-   クラスのメッセージ マップです。  
  
-   ダイアログ ボックスの標準コンス トラクターです。  
  
-   オーバーライド、 [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)メンバー関数。 この関数を編集します。 後半で説明されているとダイアログ データ交換と検証機能の使用される[ダイアログ データ エクス チェンジと検証](../mfc/dialog-data-exchange-and-validation.md)です。  
  
## <a name="see-also"></a>参照  
 [コード ウィザードによるダイアログ クラスの作成](../mfc/creating-a-dialog-class-with-code-wizards.md)   
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

