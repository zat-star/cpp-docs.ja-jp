---
title: "Adding an ATL Dialog Box | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL プロジェクト, 追加 (ダイアログ リソースを)"
  - "ダイアログ ボックス, ATL"
  - "MFC ダイアログ ボックス, ATL ダイアログ"
ms.assetid: 152a378f-7b24-4f66-aeba-c740973f03a6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Adding an ATL Dialog Box
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL ダイアログをプロジェクトに追加するには、ATL プロジェクト、または ATL サポートを含む MFC プロジェクトを用意する必要があります。  [ATL プロジェクト ウィザード](../Topic/ATL%20Project%20Wizard.md)を使用して ATL アプリケーションを作成するか、または [MFC アプリケーションに ATL オブジェクトを追加](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)して MFC アプリケーション用の ATL サポートを実装できます。  
  
 既定では、ATL ダイアログ ウィザードは [CAxDialogImpl](../Topic/CAxDialogImpl%20Class.md) クラスから派生するダイアログ ボックスを実装します。  このクラスには、ActiveX コントロールと Windows コントロールをホストするためのサポートが含まれます。  ActiveX コントロール サポートのオーバーヘッドが不要な場合は、ウィザードでコードが生成された後で、`CAxDialogImpl` クラスのすべてのインスタンスを基本クラス [CSimpleDialog](../../atl/reference/csimpledialog-class.md) または [CDialogImpl](../Topic/CDialogImpl%20Class.md) に置き換えてください。  
  
> [!NOTE]
>  `CSimpleDialog` クラスでは、Windows コモン コントロールだけをサポートするモーダル ダイアログ ボックスが作成されます。  `CDialogImpl` では、モーダル ダイアログ ボックスまたはモードレス ダイアログ ボックスのいずれかが作成されます。  
  
### プロジェクトに ATL ダイアログ リソースを追加するには  
  
1.  [ATL プロジェクト ウィザード](../Topic/ATL%20Project%20Wizard.md)を使用して ATL プロジェクトを作成します。  
  
2.  [クラス ビュー](http://msdn.microsoft.com/ja-jp/8d7430a9-3e33-454c-a9e1-a85e3d2db925)でプロジェクト名を右クリックし、ショートカット メニューの \[追加\] をクリックします。  \[クラスの追加\] をクリックします。  
  
3.  [&#91;クラスの追加&#93;](../../ide/add-class-dialog-box.md) ダイアログ ボックスのテンプレート ペインの \[ATL ダイアログ\] をクリックします。  \[開く\] をクリックして [ATL ダイアログ ウィザード](../../atl/reference/atl-dialog-wizard.md)を表示します。  
  
 詳細については、「[ダイアログ ボックスの実装](../../atl/implementing-a-dialog-box.md)」を参照してください。  
  
## 参照  
 [クラスの追加](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [ウィンドウ クラス](../Topic/ATL%20Window%20Classes.md)   
 [メッセージ マップ](../../atl/message-maps-atl.md)