---
title: "メッセージ ボックス スタイル | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MB_ICONQUESTION"
  - "MB_ICONINFORMATION"
  - "MB_DEFBUTTON2"
  - "MB_YESNO"
  - "MB_OKCANCEL"
  - "MB_TASKMODAL"
  - "MB_ICONEXCLAMATION"
  - "MB_OK"
  - "MB_DEFBUTTON3"
  - "MB_YESNOCANCEL"
  - "MB_APPLMODAL"
  - "MB_RETRYCANCEL"
  - "MB_DEFBUTTON1"
  - "MB_ABORTRETRYIGNORE"
  - "MB_SYSTEMMODAL"
  - "MB_ICONSTOP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MB_ABORTRETRYIGNORE 定数"
  - "MB_APPLMODAL 定数"
  - "MB_DEFBUTTON1 定数"
  - "MB_DEFBUTTON2 定数"
  - "MB_DEFBUTTON3 定数"
  - "MB_ICONEXCLAMATION 定数"
  - "MB_ICONINFORMATION 定数"
  - "MB_ICONQUESTION 定数"
  - "MB_ICONSTOP 定数"
  - "MB_OK 定数"
  - "MB_OKCANCEL 定数"
  - "MB_RETRYCANCEL 定数"
  - "MB_SYSTEMMODAL 定数"
  - "MB_TASKMODAL 定数"
  - "MB_YESNO 定数"
  - "MB_YESNOCANCEL 定数"
  - "メッセージ ボックス スタイル"
ms.assetid: d87014c5-4ea4-4950-a27e-7bcdda67be7d
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# メッセージ ボックス スタイル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

次のメッセージ ボックスでスタイルを使用できます。  
  
## Message\_Box の型  
  
-   **MB\_ABORTRETRYIGNORE**はメッセージ ボックスの 3 つが:プッシュ ボタンが含まれます。中止し、再試行し、無視します。  
  
-   **MB\_OK**はメッセージ ボックスの 1 つが:プッシュ ボタンが含まれます。わかりました。  
  
-   **MB\_OKCANCEL**はメッセージ ボックスの 2 つが:プッシュ ボタンが含まれます。わかりましたとします。  
  
-   **MB\_RETRYCANCEL**はメッセージ ボックスの 2 つが:プッシュ ボタンが含まれます。再試行とします。  
  
-   **MB\_YESNO**はメッセージ ボックスの 2 つが:プッシュ ボタンが含まれます。はいまたはいいえをクリックします。  
  
-   **MB\_YESNOCANCEL**はメッセージ ボックスの 3 つが:プッシュ ボタンが含まれます。はい、いいえ、およびキャンセル。  
  
## メッセージ ボックスのモーダル性  
  
-   **MB\_APPLMODAL**はメッセージ ボックスに現在のウィンドウでの作業を続行する前に、ユーザーに応答する必要があります。  ただし、ユーザーは他のアプリケーション ウィンドウに移動し、これらのウィンドウで作業できます。  既定では **MB\_SYSTEMMODAL** が **MB\_TASKMODAL** も指定しない場合 **MB\_APPLMODAL** です。  
  
-   **MB\_SYSTEMMODAL**はすべてのアプリケーション ユーザーがメッセージ ボックスに応答するまで中断されます。  システム モーダルのメッセージ ボックスに直接の目的を必要とし、頻繁に使用される深刻で \(通常は有害なユーザーにエラーを通知するために使用されます。  
  
-   **MB\_APPLMODAL**と同様ですが、Microsoft Foundation Class のアプリケーション内で使用できません**MB\_TASKMODAL**。  このフラグは、使用できるウィンドウ ハンドルがない呼び出し元のアプリケーションまたはライブラリ用に予約されています。  
  
## メッセージ ボックスのアイコン  
  
-   感嘆符のアイコンがメッセージ ボックスに表示**MB\_ICONEXCLAMATION**。  
  
-   範囲の「から成るアイコンがメッセージ ボックスに表示**MB\_ICONINFORMATION** I」。  
  
-   **MB\_ICONQUESTION** A の疑問符のアイコンがメッセージ ボックスに表示されます。  
  
-   **MB\_ICONSTOP** A のストップ記号アイコンがメッセージ ボックスに表示されます。  
  
## メッセージ ボックスの既定のボタン  
  
-   **MB\_DEFBUTTON1**は最初のボタン既定です。  **MB\_DEFBUTTON2** または **MB\_DEFBUTTON3** が指定されていない場合、最初のボタンが常に既定であることに注意してください。  
  
-   **MB\_DEFBUTTON2**は 2 番目の既定です。  
  
-   **MB\_DEFBUTTON3**は 3 番目の既定です。  
  
## 参照  
 [MFC で使用するスタイル](../../mfc/reference/styles-used-by-mfc.md)   
 [AfxMessageBox](../Topic/AfxMessageBox.md)