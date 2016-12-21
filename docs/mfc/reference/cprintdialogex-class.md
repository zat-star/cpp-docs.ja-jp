---
title: "CPrintDialogEx クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPrintDialogEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPrintDialogEx クラス"
  - "[印刷] ダイアログ ボックス"
  - "印刷設定のダイアログ ボックス"
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPrintDialogEx クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 2000 の \[印刷\] プロパティ シートに提供されるサービスをカプセル化します。  
  
## 構文  
  
```  
class CPrintDialogEx : public CCommonDialog  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CPrintDialogEx::CPrintDialogEx](../Topic/CPrintDialogEx::CPrintDialogEx.md)|`CPrintDialogEx` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CPrintDialogEx::CreatePrinterDC](../Topic/CPrintDialogEx::CreatePrinterDC.md)|印刷ダイアログ ボックスを表示せずにのプリンター デバイス コンテキストを作成します。|  
|[CPrintDialogEx::DoModal](../Topic/CPrintDialogEx::DoModal.md)|ダイアログ ボックスを表示し、フォントを選択できるようにします。|  
|[CPrintDialogEx::GetCopies](../Topic/CPrintDialogEx::GetCopies.md)|要求されたコピーの数を取得します。|  
|[CPrintDialogEx::GetDefaults](../Topic/CPrintDialogEx::GetDefaults.md)|ダイアログ ボックスを表示せずに、デバイスの既定値を取得します。|  
|[CPrintDialogEx::GetDeviceName](../Topic/CPrintDialogEx::GetDeviceName.md)|選択したプリンター デバイスの現在の名前を取得します。|  
|[CPrintDialogEx::GetDevMode](../Topic/CPrintDialogEx::GetDevMode.md)|`DEVMODE` の構造体を取得します。|  
|[CPrintDialogEx::GetDriverName](../Topic/CPrintDialogEx::GetDriverName.md)|システム定義したプリンターのデバイス ドライバー名を取得します。|  
|[CPrintDialogEx::GetPortName](../Topic/CPrintDialogEx::GetPortName.md)|選択したプリンターのポートの名前は、現在取得します。|  
|[CPrintDialogEx::GetPrinterDC](../Topic/CPrintDialogEx::GetPrinterDC.md)|プリンター デバイス コンテキストのハンドルを取得します。|  
|[CPrintDialogEx::PrintAll](../Topic/CPrintDialogEx::PrintAll.md)|ドキュメントのすべてのページを印刷するかどうかを判定します。|  
|[CPrintDialogEx::PrintCollate](../Topic/CPrintDialogEx::PrintCollate.md)|照合されたコピーが必要かどうかを判定します。|  
|[CPrintDialogEx::PrintCurrentPage](../Topic/CPrintDialogEx::PrintCurrentPage.md)|ドキュメントで現在のページを印刷するかどうかを判定します。|  
|[CPrintDialogEx::PrintRange](../Topic/CPrintDialogEx::PrintRange.md)|ページの指定範囲のみを印刷するかどうかを判定します。|  
|[CPrintDialogEx::PrintSelection](../Topic/CPrintDialogEx::PrintSelection.md)|現在選択されている項目のみを印刷するかどうかを判定します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CPrintDialogEx::m\_pdex](../Topic/CPrintDialogEx::m_pdex.md)|`CPrintDialogEx` オブジェクトをカスタマイズするために使われる構造体。|  
  
## 解説  
 フレームワークにアプリケーションの印刷プロセスの多くの部分を処理するために依存する場合があります。  フレームワークの印刷のタスクを処理するために使用方法の詳細については、" " [&#91;印刷中&#93;](../../mfc/printing.md)を参照してください。  
  
 フレームワークの干渉せずに印刷を処理するアプリケーションを作成するには、に用意されているコンストラクターで `CPrintDialogEx` のクラスを"そのまま"として使用できます。また、`CPrintDialogEx` から独自のダイアログ クラスを派生し、必要に応じたコンストラクターを記述できます。  どちらの場合も、これらのダイアログ ボックスは、標準の MFC ダイアログ ボックスに似たクラスから派生するため `CCommonDialog`します。  
  
 `CPrintDialogEx` のオブジェクトを使用するには、最初に `CPrintDialogEx` のコンストラクターを使用してオブジェクトを作成します。  ダイアログ ボックスが構築されたら、ダイアログ ボックスのコントロールの値を初期化するに [m\_pdex](../Topic/CPrintDialogEx::m_pdex.md) の構造体の値を設定または変更できます。  `m_pdex` の構造は、型 [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844)です。  この構造体の詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] を参照してください。  
  
 **hDevMode** と **hDevNames** のメンバーの `m_pdex` の独自のハンドルを指定しなかった場合は、ダイアログ ボックスが完了したときに、これらのハンドルの Windows 関数 **GlobalFree** を呼び出すください。  
  
 ダイアログ ボックスのコントロールを初期化したら、ダイアログ ボックスを表示してユーザーが印刷オプションを選択できるように `DoModal` のメンバー関数を呼び出します。  `DoModal` が返されるとき、ユーザーが\[OK\]を選択するか、追加、またはボタンを取り消すかどうかを確認できます。  
  
 ユーザーが\[OK\]押したら、ユーザーに入力された情報を取得するために `CPrintDialogEx` のメンバー関数を使用できます。  
  
 `CPrintDialogEx::GetDefaults` のメンバー関数は、ダイアログ ボックスを表示せずに、現在のプリンターの既定値を取得する場合に役立ちます。  このメソッドは、ユーザーの操作を必要としません。  
  
 Windows の **CommDlgExtendedError** 関数を使用すると、ダイアログ ボックスの初期化中にエラーが発生したかどうかを確認し、そのエラーについての情報を取得できます。  この関数の詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] を参照してください。  
  
 `CPrintDialogEx` の使い方の詳細については、「[コモン ダイアログ クラス](../../mfc/common-dialog-classes.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `IObjectWithSite`  
  
 `IPrintDialogCallback`  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 `CPrintDialogEx`  
  
## 必要条件  
 **ヘッダー:** afxdlgs.h  
  
## 参照  
 [CCommonDialog クラス](../Topic/CCommonDialog%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPrintInfo 構造体](../../mfc/reference/cprintinfo-structure.md)