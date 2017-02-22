---
title: "CMFCKeyMapDialog クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCKeyMapDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCKeyMapDialog クラス"
ms.assetid: 5feb4942-d636-462d-a162-0104dd320f4e
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CMFCKeyMapDialog クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCKeyMapDialog` クラスは、キーボードのキーにコマンドをマップするコントロールをサポートします。  
  
## 構文  
  
```  
class CMFCKeyMapDialog : public CDialogEx  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCKeyMapDialog::CMFCKeyMapDialog](../Topic/CMFCKeyMapDialog::CMFCKeyMapDialog.md)|`CMFCKeyMapDialog` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCKeyMapDialog::DoModal](../Topic/CMFCKeyMapDialog::DoModal.md)|キーボード マップ ダイアログ ボックスを表示します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCKeyMapDialog::FormatItem](../Topic/CMFCKeyMapDialog::FormatItem.md)|キー マップを示す文字列を構築するために、フレームワークによって呼び出されます。  既定では、コマンド名、使用するショートカット キー、およびショートカット キーの説明が文字列に含まれます。|  
|[CMFCKeyMapDialog::GetCommandKeys](../Topic/CMFCKeyMapDialog::GetCommandKeys.md)|指定したコマンドに関連付けられているショートカット キーのリストが含まれている文字列を取得します。|  
|[CMFCKeyMapDialog::OnInsertItem](../Topic/CMFCKeyMapDialog::OnInsertItem.md)|キーボード マップ コントロールをサポートする内部リスト コントロールに新しい項目を挿入する前に、フレームワークによって呼び出されます。|  
|[CMFCKeyMapDialog::OnPrintHeader](../Topic/CMFCKeyMapDialog::OnPrintHeader.md)|新しいページのキーボード マップのヘッダーを印刷するために、フレームワークによって呼び出されます。|  
|[CMFCKeyMapDialog::OnPrintItem](../Topic/CMFCKeyMapDialog::OnPrintItem.md)|キーボード割り当て項目を印刷するために、フレームワークによって呼び出されます。|  
|[CMFCKeyMapDialog::OnSetColumns](../Topic/CMFCKeyMapDialog::OnSetColumns.md)|キーボード マップ コントロールをサポートする内部リスト コントロール内の列のキャプションを設定するために、フレームワークによって呼び出されます。|  
|[CMFCKeyMapDialog::PrintKeyMap](../Topic/CMFCKeyMapDialog::PrintKeyMap.md)|ユーザーが **\[印刷\]** ボタンをクリックしたときに、フレームワークによって呼び出されます。|  
|[CMFCKeyMapDialog::SetColumnsWidth](../Topic/CMFCKeyMapDialog::SetColumnsWidth.md)|キーボード マップ コントロールをサポートする内部リスト コントロール内の列の幅を設定するために、フレームワークによって呼び出されます。|  
  
## 解説  
 サイズを変更できるキーボード マップ ダイアログ ボックスを実装するには、`CMFCKeyMapDialog` クラスを使用します。  このダイアログ ボックスはリスト ビュー コントロールを使用して、キーボード ショートカットとそれに関連するコマンドを表示します。  
  
 アプリケーションで `CMFCKeyMapDialog` クラスを使用するには、メイン フレーム ウィンドウへのポインターを `CMFCKeyMapDialog` コンストラクターにパラメーターとして渡します。  その後、`DoModal` メソッドを呼び出してモーダル ダイアログ ボックスを開始します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCKeyMapDialog](../../mfc/reference/cmfckeymapdialog-class.md)  
  
## 必要条件  
 **ヘッダー :** afxkeymapdialog.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CKeyboardManager クラス](../../mfc/reference/ckeyboardmanager-class.md)