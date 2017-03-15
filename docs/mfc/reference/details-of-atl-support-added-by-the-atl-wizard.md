---
title: "ATL ウィザードで追加した ATL サポートの詳細 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.atl.support"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, MFC プロジェクト"
  - "MFC, ATL サポート"
ms.assetid: aa66bad0-008f-4886-94c1-2a0a0d04bce4
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ATL ウィザードで追加した ATL サポートの詳細
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[既存の MFC 実行可能ファイルまたは DLL に ATL サポートを追加](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)すると、Visual C\+\+ によって既存の MFC プロジェクトに以下の変更が加えられます。この例でのプロジェクト名は `MFCEXE` です。  
  
-   サーバーの登録に使用する .idl ファイルと .rgs ファイルが追加されます。  
  
-   メイン アプリケーションのヘッダー ファイルと実装ファイル \(Mfcexe.h と Mfcexe.cpp\) に新規クラス \(**CAtlMFCModule** の派生クラス\) が追加されます。  この新しいクラスのほかにも、登録に必要なコードが `InitInstance` 関数に追加されます。  `ExitInstance` 関数にも、クラス オブジェクトを無効にするためのコードが追加されます。  最後に、ヘッダー ファイルでは、2 つの新しいヘッダー ファイル \(Initguid.h と Mfcexe\_i.c\) が実装ファイルにインクルードされ、**CAtlMFCModule** の派生クラスに対する新しい GUID が宣言および初期化されます。  
  
-   サーバーを適切に登録するために、新しい .rgs ファイルのエントリがプロジェクトのリソース ファイルに追加されます。  
  
## DLL プロジェクトに関するメモ  
 MFC DLL プロジェクトに ATL サポートを追加する場合は、異なる点がいくつかあります。  DLL を登録または登録解除するために、**DLLRegisterServer** 関数と **DLLUnregisterServer** 関数にコードが追加されます。  また、[DllCanUnloadNow](../Topic/CAtlDllModuleT::DllCanUnloadNow.md) と [DllGetClassObject](../Topic/CAtlDllModuleT::DllGetClassObject.md) にもコードが追加されます。  
  
## 参照  
 [MFC プロジェクトでの ATL のサポート](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)   
 [コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [クラスの追加](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)   
 [メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)   
 [仮想関数のオーバーライド](../Topic/Overriding%20a%20Virtual%20Function%20\(Visual%20C++\).md)   
 [MFC メッセージ ハンドラー](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [クラス各部へのジャンプ](../../ide/navigating-the-class-structure-visual-cpp.md)