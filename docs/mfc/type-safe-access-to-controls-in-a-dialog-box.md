---
title: "ダイアログ ボックスのコントロールへのタイプ セーフ アクセス |Microsoft ドキュメント"
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
- common controls [MFC], in dialog boxes
- Windows common controls [MFC], in dialog boxes
- safe access to dialog box controls
- dialog boxes [MFC], type-safe access to controls
- controls [MFC], accessing in dialog boxes
- type-safe access to dialog box controls
- MFC dialog boxes [MFC], type-safe access to controls
ms.assetid: 67021025-dd93-4d6a-8bed-a1348fe50685
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b6005f34b28a634b36aad93186a34a8806b8033d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="type-safe-access-to-controls-in-a-dialog-box"></a>ダイアログ ボックスのコントロールへのタイプ セーフ アクセス
ダイアログ ボックス内のコントロールは、`CListBox` や `CEdit` などの、MFC コントロール クラスのインターフェイスを使用できます。 コントロール オブジェクトを作成してダイアログ コントロールに追加することができます。 追加すると、クラス インターフェイスを通じてコントロールにアクセスできます (コントロール上で動作するメンバー関数を呼び出します)。 ここで説明する各メソッドは、コントロールに対してタイプ セーフなアクセスが可能です。 これは、エディット ボックスやリスト ボックスなどのコントロールで特に役立ちます。  
  
 ダイアログ ボックス内のコントロールと、`CDialog` 派生クラス内の C++ コントロール メンバー変数とを接続するには、次の 2 つの方法があります。  
  
-   [コード ウィザードを使用しません。](../mfc/type-safe-access-to-controls-without-code-wizards.md)  
  
-   [コード ウィザードを使用](../mfc/type-safe-access-to-controls-with-code-wizards.md)  
  
## <a name="see-also"></a>参照  
 [ダイアログ ボックス](../mfc/dialog-boxes.md)

