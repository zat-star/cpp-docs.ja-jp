---
title: "CPageSetupDialog クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPageSetupDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPageSetupDialog クラス"
  - "OLE の [ページ設定] ダイアログ ボックス"
  - "ページ設定"
  - "[ページ設定] ダイアログ ボックス"
  - "印刷設定のダイアログ ボックス"
ms.assetid: 049c0ac8-f254-4854-9414-7a8271d1447a
caps.latest.revision: 24
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPageSetupDialog クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

印刷マージンの設定や変更の追加サポートと共に \[OLE ページの設定\] ダイアログ ボックスにより提供されるサービスをカプセル化します。  
  
## 構文  
  
```  
class CPageSetupDialog : public CCommonDialog  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CPageSetupDialog::CPageSetupDialog](../Topic/CPageSetupDialog::CPageSetupDialog.md)|`CPageSetupDialog` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CPageSetupDialog::CreatePrinterDC](../Topic/CPageSetupDialog::CreatePrinterDC.md)|印刷のデバイス コンテキストを作成します。|  
|[CPageSetupDialog::DoModal](../Topic/CPageSetupDialog::DoModal.md)|ダイアログ ボックスを表示してユーザーが選択されますができます。|  
|[CPageSetupDialog::GetDeviceName](../Topic/CPageSetupDialog::GetDeviceName.md)|プリンターのデバイス名を返します。|  
|[CPageSetupDialog::GetDevMode](../Topic/CPageSetupDialog::GetDevMode.md)|プリンターの現在の `DEVMODE` を返します。|  
|[CPageSetupDialog::GetDriverName](../Topic/CPageSetupDialog::GetDriverName.md)|プリンターで使用するドライバーを返します。|  
|[CPageSetupDialog::GetMargins](../Topic/CPageSetupDialog::GetMargins.md)|プリンターの現在のマージンの設定を返します。|  
|[CPageSetupDialog::GetPaperSize](../Topic/CPageSetupDialog::GetPaperSize.md)|のプリンター用紙サイズを返します。|  
|[CPageSetupDialog::GetPortName](../Topic/CPageSetupDialog::GetPortName.md)|出力ポートの名前を返します。|  
|[CPageSetupDialog::OnDrawPage](../Topic/CPageSetupDialog::OnDrawPage.md)|印刷されたページの映像を表示するために、フレームワークによって呼び出されます。|  
|[CPageSetupDialog::PreDrawPage](../Topic/CPageSetupDialog::PreDrawPage.md)|印刷されたページの映像を表示する前に、フレームワークによって呼び出されます。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CPageSetupDialog::m\_psd](../Topic/CPageSetupDialog::m_psd.md)|`CPageSetupDialog` オブジェクトをカスタマイズするために使われる構造体。|  
  
## 解説  
 このクラスは、印刷設定\]ダイアログ ボックスの位置を受け取るように設計されています。  
  
 `CPageSetupDialog` のオブジェクトを使用するには、最初に `CPageSetupDialog` のコンストラクターを使用してオブジェクトを作成します。  ダイアログ ボックスが構築されたら、ダイアログ ボックスのコントロールの値を初期化するに `m_psd` データ メンバーの値を設定または変更できます。  [m\_psd](../Topic/CPageSetupDialog::m_psd.md) の構造は、型 **PAGESETUPDLG**です。  
  
 ダイアログ ボックスのコントロールを初期化したら、ダイアログ ボックスを表示してユーザーが印刷オプションを選択できるように `DoModal` のメンバー関数を呼び出します。  `DoModal` は、ユーザーが \[OK\] \(**IDOK**\) ボタンと \[キャンセル\] \(**IDCANCEL**\) ボタンのどちらをクリックしたかを返します。  
  
 `DoModal` **IDOK**がを返す場合、`CPageSetupDialog` のメンバー関数を複数使用するか、ユーザーに入力された情報を取得するに `m_psd` のデータ メンバーにアクセスします。  
  
> [!NOTE]
>  共通の OLE ページの設定\]ダイアログ ボックスを閉じた後、ユーザーが行った変更は、フレームワークによって保存されません。  これは、アプリケーション自体までこのダイアログ ボックスでは、アプリケーションのドキュメントまたはアプリケーションでクラスのメンバーなどの永続的な位置に値を保存できます。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 `CPageSetupDialog`  
  
## 必要条件  
 **ヘッダー:** afxdlgs.h  
  
## 参照  
 [MFC WORDPAD サンプル](../../top/visual-cpp-samples.md)   
 [CCommonDialog クラス](../Topic/CCommonDialog%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)