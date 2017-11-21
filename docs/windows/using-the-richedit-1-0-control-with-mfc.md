---
title: "MFC での RichEdit 1.0 コントロールの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- RichEdit 1.0 control
- rich edit controls, RichEdit 1.0
ms.assetid: 5a9060dd-44d8-4ef3-956e-16152f7e23d2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f8085eb8b28ece4f0ca24d00c33b8809aa412da5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="using-the-richedit-10-control-with-mfc"></a>MFC でのリッチ エディット 1.0 コントロールの使用
リッチ エディット コントロールを使用するには、まず[AfxInitRichEdit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2)リッチ エディット 2.0 コントロール (RICHED20 を読み込めません。DLL)、または呼び出す[AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit)古い RichEdit 1.0 コントロール (RICHED32 を読み込めません。DLL) です。  
  
 現在を使用することは[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)古い RichEdit 1.0 コントロールが、クラスが**CRichEditCtrl**はのみリッチ エディット 2.0 コントロールをサポートするために設計されています。 RichEdit 1.0 およびリッチ エディット 2.0 は、非常に似ていますが、ために、ほとんどのメソッドを使用します。ただしは、1.0 と 2.0 のコントロールをいくつかのメソッドが正常に動作しない可能性がありますまたはまったく動作しないようにいくつか違いがあります。  
  
## <a name="requirements"></a>要件  
 MFC  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ エディターのトラブルシューティング](../windows/troubleshooting-the-dialog-editor.md)   
 [ダイアログ エディター](../windows/dialog-editor.md)

