---
title: "DEVNAMES 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DEVNAMES"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DEVNAMES"
ms.assetid: aac97f60-2169-471a-ba5d-c0baed9eed9a
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DEVNAMES 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`DEVNAMES` 構造体のプリンター ドライバー、デバイス名とポートを識別する文字列を示します。  
  
## 構文  
  
```  
  
      typedef struct tagDEVNAMES { /* dvnm */  
    WORD wDriverOffset;  
    WORD wDeviceOffset;  
    WORD wOutputOffset;  
    WORD wDefault;  
    /* driver, device, and port-name strings follow wDefault */  
} DEVNAMES;  
```  
  
#### パラメーター  
 *wDriverOffset*  
 \(入出力\) デバイス ドライバーのファイル名 \(拡張子なし\) を含む null で終わる文字列への文字のオフセットを指定します。  入力のプリンターを決定するために、ダイアログ ボックスに表示するには、この文字列が使用されます。  
  
 *wDeviceOffset*  
 \(入出力\) デバイス名を含む null で終わる文字列 \(最大空白を含む 32 バイト\) に文字のオフセットを指定します。  この文字列は [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) 構造体の **dmDeviceName** のメンバーと同じである必要があります。  
  
 *wOutputOffset*  
 \(入出力\) 物理出力メディア \(出力ポート\) の DOS のデバイス名を含む null で終わる文字列への文字のオフセットを指定します。  
  
 *wDefault*  
 `DEVNAMES` 構造体に含まれる文字列が既定のプリンターを識別するかどうかを指定します。  この文字列は、既定のプリンターが最後の印刷操作から変更されていないことを確認するために使用されます。  入力時には、**DN\_DEFAULTPRN** フラグが設定されている場合、`DEVNAMES` 構造体の他の値は現在の既定のプリンターに照らしてチェックされます。  文字列のいずれかに一致する、ユーザーに通知するドキュメントが書式設定し直す必要があるという警告メッセージが表示されます。  出力では、**wDefault** のメンバーは印刷設定ダイアログ ボックスが表示され、ユーザーが OK ボタンをクリックした場合にのみ変更されます。  **DN\_DEFAULTPRN** フラグを既定のプリンターを選択して設定されます。  特定のプリンターを選択した場合、フラグは設定されません。  このメンバーのそのほかのビットはすべて印刷ダイアログ ボックス プロシージャが内部で使用するために予約されています。  
  
## 解説  
 **PrintDlg** 関数は、システム定義の印刷ダイアログ ボックスのメンバーを初期化するには、これらの文字列を使用します。  ユーザーがダイアログ ボックスを閉じると、選択したプリンターに関する情報はこの構造で返されます。  
  
## 必要条件  
 **ヘッダー:** commdlg.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPrintDialog::CreatePrinterDC](../Topic/CPrintDialog::CreatePrinterDC.md)