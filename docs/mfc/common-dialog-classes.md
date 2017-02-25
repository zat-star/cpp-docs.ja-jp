---
title: "コモン ダイアログ クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コモン ダイアログ ボックス [C++]"
  - "コモン ダイアログ ボックス [C++], コモン ダイアログ クラス"
  - "コモン ダイアログ クラス [C++]"
  - "ダイアログ ボックス [C++], Windows コモン ダイアログ"
  - "ダイアログ クラス [C++]"
  - "ダイアログ クラス [C++], コモン"
  - "MFC ダイアログ ボックス, Windows コモン ダイアログ"
  - "Windows コモン ダイアログ [C++]"
ms.assetid: 5c4f6443-896c-4b05-a7df-8169fdadc71d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# コモン ダイアログ クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラス [CDialog](../mfc/reference/cdialog-class.md)に加えて、MFC には次の表に示すように `CDialog` から派生される一般的なダイアログ ボックスをカプセル化する複数のクラスが用意されています。  カプセル化されたダイアログ ボックスは「コモン ダイアログ ボックス」とも呼ばれ、Windows コモン ダイアログのライブラリ \(COMMDLG.DLL\) の一部です。  これらのクラスのダイアログ テンプレート リソースとコードは、Windows Versions 3.1 以降の一部である Windows コモン ダイアログ ボックスで指定します。  
  
### コモン ダイアログ クラス  
  
|派生ダイアログ クラス|目的|  
|-----------------|--------|  
|[CColorDialog](../mfc/reference/ccolordialog-class.md)|ユーザーの色を許可します。|  
|[CFileDialog](../Topic/CFileDialog%20Class.md)|ユーザーがファイル名を開いたり保存したりするために選択できるようにします。|  
|[CFindReplaceDialog](../Topic/CFindReplaceDialog%20Class.md)|ユーザーを検索を開始またはテキスト ファイルの操作を置き換えることができます。|  
|[CFontDialog](../mfc/reference/cfontdialog-class.md)|ユーザーがフォントを指定できるようにします。|  
|[CPrintDialog](../Topic/CPrintDialog%20Class.md)|ユーザーが印刷ジョブについての情報を指定することができます。|  
|[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)|Windows 2000 の印刷プロパティ シート。|  
  
 コモン ダイアログ クラスの詳細については、" *MFC リファレンス"の*対応する個々のクラス名を参照します。  MFC は、OLE に使用されるいくつかの標準ダイアログ クラスが用意されています。  これらのクラスの詳細については、基本クラスは、" *MFC リファレンス"の*" [COleDialog](../mfc/reference/coledialog-class.md)、を参照してください。  
  
 MFC の 3 つが他のクラスには、ダイアログ形式の特性があります。  [CFormView](../mfc/reference/cformview-class.md)クラスについては、[CRecordView](../mfc/reference/crecordview-class.md)と [CDaoRecordView クラス](../mfc/reference/cdaorecordview-class.md)は、" *MFC リファレンス"の*"クラスを参照します。  [CDialogBar](../mfc/reference/cdialogbar-class.md)クラスについては、[ダイアログ バー](../mfc/dialog-bars.md)を参照してください。  
  
## 参照  
 [ダイアログ ボックス](../mfc/dialog-boxes.md)   
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)   
 [OLE のダイアログ ボックス](../mfc/dialog-boxes-in-ole.md)