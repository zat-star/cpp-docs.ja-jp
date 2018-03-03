---
title: "リッチ エディット コントロールに段落の書式 |Microsoft ドキュメント"
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
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f0dc12d923f6f424fe84768b0d934d8dd7ff20b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>リッチ エディット コントロールでの段落書式の設定
リッチ エディット コントロールのメンバー関数を使用することができます ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) の書式情報を取得して段落の書式を設定します。 段落の書式設定属性には、配置、タブ、インデント、および番号が含まれます。  
  
 段落を使用して書式を適用することができます、 [SetParaFormat](../mfc/reference/cricheditctrl-class.md#setparaformat)メンバー関数。 現在の段落を選択したテキストの書式設定を確認するには[GetParaFormat](../mfc/reference/cricheditctrl-class.md#getparaformat)メンバー関数。 [PARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787940)構造がこれらのメンバー関数で使用を段落属性を指定します。 重要なメンバーのいずれかの**PARAFORMAT**は**dwMask**です。 `SetParaFormat`、 **DwMask**段落属性はこの関数の呼び出しで設定されますを指定します。 `GetParaFormat`レポートの選択範囲の最初の段落の属性**dwMask**選択範囲全体で一貫性のある属性を指定します。  
  
## <a name="see-also"></a>参照  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

