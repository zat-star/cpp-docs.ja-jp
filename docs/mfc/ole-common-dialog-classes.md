---
title: "OLE コモン ダイアログ クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX クラス [C++]"
  - "コモン ダイアログ クラス"
  - "ダイアログ クラス [C++], OLE"
  - "OLE コモン ダイアログ クラス [C++]"
ms.assetid: 706526ae-f94f-4909-a0f8-6b5fe954fd97
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# OLE コモン ダイアログ クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これらのクラスは、いくつかの標準 OLE ダイアログ ボックスの実装に、共通の OLE タスクを処理します。  また、OLE 機能に一貫したユーザー インターフェイスを提供します。  
  
 [COleDialog](../mfc/reference/coledialog-class.md)  
 すべての OLE ダイアログ ボックスの一般的な実装を格納するために、フレームワークによって使用されます。  ユーザー カテゴリのすべてのダイアログ ボックス クラスは、この基本クラスから派生されます。  `COleDialog` を直接 使用することはできません。  
  
 [COleInsertDialog](../mfc/reference/coleinsertdialog-class.md)  
 オブジェクトの挿入ダイアログ ボックスで、新しい OLE リンクされたまたは埋め込まれたアイテムを挿入するための標準のユーザー インターフェイスが表示されます。  
  
 [COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md)  
 貼り付け時に特殊なダイアログ ボックス、編集の貼り付けコマンドを実装するための標準的なユーザー インターフェイスが表示されます。  
  
 [COleLinksDialog](../mfc/reference/colelinksdialog-class.md)  
 Edit リンク ダイアログ ボックス、リンクされた項目に関する変更情報の標準のユーザー インターフェイスが表示されます。  
  
 [COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md)  
 変更アイコン ダイアログ ボックス、埋め込まれた OLE のまたはリンク アイテムに関連付けられているアイコンを変更するための標準のユーザー インターフェイスが表示されます。  
  
 [COleConvertDialog](../mfc/reference/coleconvertdialog-class.md)  
 変換ダイアログ ボックス、1 種類のから別のプロジェクトに OLE アイテムを変換するための標準のユーザー インターフェイスが表示されます。  
  
 [COlePropertiesDialog](../Topic/COlePropertiesDialog%20Class.md)  
 Windows に共通の OLE プロパティ ダイアログ ボックスをカプセル化します。  共通の OLE プロパティ ダイアログ ボックスは、Windows の標準に準拠した OLE ドキュメント アイテムのプロパティを表示および変更するための簡単な方法を提供します。  
  
 [COleUpdateDialog](../Topic/COleUpdateDialog%20Class.md)  
 更新ダイアログ ボックス、ドキュメントのすべてのリンクを更新するための標準的なユーザー インターフェイスが表示されます。  ダイアログ ボックスを閉じる更新プロシージャが完了に示す、プログレス インジケーターが含まれます。  
  
 [COleChangeSourceDialog](../mfc/reference/colechangesourcedialog-class.md)  
 ソースの変更ダイアログ ボックスで、リンク先またはソースを変更するための標準のユーザー インターフェイスが表示されます。  
  
 [COleBusyDialog](../mfc/reference/colebusydialog-class.md)  
 使用するサーバーを表示し、ダイアログ ボックスを応答しないサーバーがビジー アプリケーションに処理の標準ユーザー インターフェイス呼び出します。  通常 `COleMessageFilter` の実装によって自動的に表示されます。  
  
## 参照  
 [クラスの概要](../mfc/class-library-overview.md)