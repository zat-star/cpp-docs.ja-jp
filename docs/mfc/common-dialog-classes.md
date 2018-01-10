---
title: "コモン ダイアログ クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dialog classes [MFC]
- dialog boxes [MFC], Windows common dialogs
- common dialog boxes [MFC], common dialog classes
- common dialog classes [MFC]
- MFC dialog boxes [MFC], Windows common dialogs
- Windows common dialogs [MFC]
- dialog classes [MFC], common
- common dialog boxes [MFC]
ms.assetid: 5c4f6443-896c-4b05-a7df-8169fdadc71d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fcbed7cec501257f03ab13447d54e081c1d46c76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="common-dialog-classes"></a>コモン ダイアログ クラス
クラスに加えて[CDialog](../mfc/reference/cdialog-class.md)、MFC から派生したいくつかのクラスを提供`CDialog`をカプセル化する一般的に使用されるダイアログ ボックスに、次の表に示すようにします。 カプセル化されたダイアログ ボックスが「一般的なダイアログ ボックス」と呼ばれます、ライブラリの一部、Windows コモン ダイアログ (COMMDLG です。DLL) です。 ダイアログ テンプレート リソースと、これらのクラスのコードは、Windows 3.1 以降のバージョンの一部である共通のダイアログ ボックスに、Windows で説明します。  
  
### <a name="common-dialog-classes"></a>コモン ダイアログ クラス  
  
|派生ダイアログ クラス|目的|  
|--------------------------|-------------|  
|[CColorDialog](../mfc/reference/ccolordialog-class.md)|により、ユーザーが色を選択できます。|  
|[CFileDialog](../mfc/reference/cfiledialog-class.md)|ユーザーが開くまたは保存するファイル名を選択できます。|  
|[CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)|ユーザーを指定して検索を開始するか、置換テキスト ファイルに操作できます。|  
|[CFontDialog](../mfc/reference/cfontdialog-class.md)|ユーザーが、フォントを指定できます。|  
|[CPrintDialog](../mfc/reference/cprintdialog-class.md)|ユーザーが印刷ジョブの情報を指定できます。|  
|[メンバー](../mfc/reference/cprintdialogex-class.md)|Windows 2000 の印刷プロパティ シートです。|  
  
 コモン ダイアログ クラスの詳細については、内の個々 のクラス名を参照してください、 *『 MFC リファレンス*です。 MFC では、OLE の標準的なダイアログ クラスの数も提供します。 これらのクラスについては、基本クラスを参照してください。[関数](../mfc/reference/coledialog-class.md)で、 *『 MFC リファレンス*です。  
  
 その他の 3 つの MFC クラスでは、ダイアログのような特性があります。 クラスについて[CFormView](../mfc/reference/cformview-class.md)、 [CRecordView](../mfc/reference/crecordview-class.md)、および[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)、クラスを参照してください、 *『 MFC リファレンス*です。 クラスについては[CDialogBar](../mfc/reference/cdialogbar-class.md)を参照してください[ダイアログ バー](../mfc/dialog-bars.md)です。  
  
## <a name="see-also"></a>参照  
 [ダイアログ ボックス](../mfc/dialog-boxes.md)   
 [ダイアログ ボックスのライフ サイクル](../mfc/life-cycle-of-a-dialog-box.md)   
 [OLE のダイアログ ボックス](../mfc/dialog-boxes-in-ole.md)

