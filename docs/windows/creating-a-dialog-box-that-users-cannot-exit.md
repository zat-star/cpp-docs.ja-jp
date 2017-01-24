---
title: "Creating a Dialog Box That Users Cannot Exit | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "dialog boxes, creating"
  - "modal dialog boxes, logon screens"
  - "logon screens"
ms.assetid: 54823c27-1658-4388-bd12-0a1ce8f3899e
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a Dialog Box That Users Cannot Exit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ユーザーには終了できない実行時ダイアログ ボックスを作成できます。 この種のダイアログ ボックスはログオンの場合や、アプリケーションやドキュメントをロックする場合に便利です。  
  
### ユーザーには終了できないダイアログ ボックスを作成するには  
  
1.  ダイアログ ボックスの **\[プロパティ\]** ウィンドウで、**\[システム メニュー\]** プロパティを **\[false\]** に設定します。  
  
     これによって、ダイアログ ボックスのシステム メニューと **\[閉じる\]** ボタンが無効になります。  
  
2.  ダイアログ ボックスのフォームで、**\[キャンセル\]** ボタンと **\[OK\]** ボタンを削除します。  
  
     実行時にユーザーはこれらの特性を持つモーダル ダイアログ ボックスを終了できません。  
  
 この種のダイアログ ボックスをテストできるようにするため、Esc キーが押されると、ダイアログ ボックスのテスト機能がそれを検出します。 \(Esc キーは、VK\_ESCAPE 仮想キーとも呼ばれます。\) 実行時にどのように動作するよう設計されているかに関わりなく、テスト モードで Esc キーを押すとダイアログ ボックスは終了します。  
  
> [!NOTE]
>  MFC アプリケーションの場合、ユーザーが終了できないダイアログ ボックスを作成するには、`OnOK`と `OnCancel` の既定の動作をオーバーライドする必要があります。それらに関連付けられたボタンを削除しても、Enter キーまたは Esc キーを押せばダイアログ ボックスを終了できるためです。  
  
 マネージ プロジェクトにリソースを追加する方法については、「[デスクトップ アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」をご覧ください。  
  
## 必要条件  
 Win32  
  
## 参照  
 [How to: Create a Resource](../windows/how-to-create-a-resource.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Dialog Editor](../mfc/dialog-editor.md)