---
title: "ActiveX コントロール コンテナー: ActiveX コントロールをメンバー変数に接続する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- ActiveX controls [MFC], member variables of project
- connecting ActiveX controls to container member variables
- ActiveX controls [MFC], accessing
- member variables [MFC], ActiveX controls in project
- ActiveX control containers [MFC], ActiveX controls as member variables
ms.assetid: 7898a336-440d-4a60-be43-cb062b807aee
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2248dd68b0ecc7471899552bcb7b0394f3f9f363
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="activex-control-containers-connecting-an-activex-control-to-a-member-variable"></a>ActiveX コントロール コンテナー : ActiveX コントロールとメンバー変数の関連付け
コントロール コンテナー アプリケーション内での ActiveX コントロールにアクセスする最も簡単な方法は、ActiveX コントロールにコントロールを含むダイアログ クラスのメンバー変数を関連付けるにです。  
  
> [!NOTE]
>  これは、コンテナー クラス内から埋め込みコントロールにアクセスする唯一の方法ではありませんが、この記事の目的で十分です。  
  
### <a name="adding-a-member-variable-to-the-dialog-class"></a>ダイアログ クラスにメンバー変数の追加  
  
1.  クラス ビューから、ショートカット メニューを開くメイン ダイアログ クラスを右クリックします。 たとえば、`CContainerDlg` のようにします。  
  
2.  ショートカット メニューから **追加**し**変数の追加**です。  
  
3.  メンバー変数の追加ウィザード をクリックして**制御変数**です。  
  
4.  **コントロール ID**ボックスの一覧で、埋め込みの ActiveX コントロールのコントロール ID を選択します。 たとえば、`IDC_CIRCCTRL1` のようにします。  
  
5.  **変数名**ボックスで、名前を入力します。  
  
     たとえば、`m_circctl` のようにします。  
  
6.  をクリックして**完了**選択内容を確定し、メンバー変数の追加ウィザードを終了します。  
  
## <a name="see-also"></a>参照  
 [ActiveX コントロール コンテナー](../mfc/activex-control-containers.md)

