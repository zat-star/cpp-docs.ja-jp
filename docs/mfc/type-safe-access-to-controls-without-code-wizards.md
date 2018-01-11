---
title: "コード ウィザードを使用しないコントロールへのタイプ セーフ アクセス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dialog boxes [MFC], accessing controls
- dialog box controls [MFC], accessing
ms.assetid: 325b4927-d49b-42b4-8e0b-fc84f31fb059
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0c5a4adce63851620326add61857433b32e1fad5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="type-safe-access-to-controls-without-code-wizards"></a>コード ウィザードを使用しない、コントロールへのタイプ セーフ アクセス
コントロールへのタイプ セーフなアクセスを作成するための最初の方法は、クラスの戻り値の型をキャストするインライン メンバー関数を使用して`CWnd`の`GetDlgItem`適切な C++ コントロール型に、この例のように、メンバー関数。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#50](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_1.cpp)]  
  
 このメンバー関数を使用して、次のようなコードでタイプ セーフな方法でコントロールにアクセスできます。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#51](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_2.cpp)]  
  
## <a name="see-also"></a>参照  
 [ダイアログ ボックスのコントロールへのタイプ セーフ アクセス](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)   
 [コード ウィザードを使用した、コントロールへのタイプ セーフ アクセス](../mfc/type-safe-access-to-controls-with-code-wizards.md)

