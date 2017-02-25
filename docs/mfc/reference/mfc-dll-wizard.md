---
title: "MFC DLL ウィザード | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.dll.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL ウィザード [MFC]"
  - "DLL [C++], 作成"
  - "DLL [C++], MFC"
  - "MFC DLL ウィザード"
  - "MFC DLL [C++]"
  - "MFC DLL [C++], 作成"
ms.assetid: 4e936031-7e39-4f40-a295-42a09c5ff264
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# MFC DLL ウィザード
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC DLL ウィザードで MFC DLL プロジェクトを作成すると、機能が組み込まれた、作業用の初期アプリケーションが作成されます。このアプリケーションをコンパイルすると、[DLL](../../build/dlls-in-visual-cpp.md) の基本機能が実装されます。  MFC の初期プログラムには、C\+\+ ソース \(.cpp\) ファイル、リソース \(.rc\) ファイル、およびプロジェクト \(.vcxproj\) ファイルが含まれます。  これらの初期ファイルで生成されたコードは、MFC に基づいています。  詳細については、Visual Studio でプロジェクト用に生成された Readme.txt のファイルの説明、および「[MFC DLL ウィザードによって生成されるクラスと関数](../Topic/Classes%20and%20Functions%20Generated%20by%20the%20MFC%20DLL%20Wizard.md)」を参照してください。  
  
## 概要  
 ウィザードのこのページでは、作成する [MFC DLL プロジェクトのアプリケーション設定](../../mfc/reference/application-settings-mfc-dll-wizard.md)の現在値が示されます。  既定では、プロジェクトは、設定が追加されない標準 DLL \(MFC 共有\) プロジェクトとして作成されます。  
  
 これらの既定値を変更するには、ウィザードの左の列にある **\[アプリケーションの設定\]** をクリックし、MFC DLL ウィザードの \[アプリケーションの設定\] ページを使用します。  
  
 MFC DLL プロジェクトを作成した後で、Visual C\+\+ の[コード ウィザード](../../ide/adding-functionality-with-code-wizards-cpp.md)を使用して、プロジェクトにオブジェクトやコントロールを追加できます。  
  
 基本の MFC DLL プロジェクトに以下のタスクを実行して機能を強化できます。  
  
-   [DLL からのエクスポート](../../build/exporting-from-a-dll.md)  
  
-   [DLL と実行形式のリンク](../../build/linking-an-executable-to-a-dll.md)  
  
-   [DLL の初期化](../../build/initializing-a-dll.md)  
  
## 参照  
 [Visual C\+\+ プロジェクトの作成および管理](../../ide/creating-and-managing-visual-cpp-projects.md)   
 [プロパティ ページ](../../ide/property-pages-visual-cpp.md)   
 [プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)   
 [Deploying Applications](http://msdn.microsoft.com/ja-jp/4ff8881d-0daf-47e7-bfe7-774c625031b4)   
 [MFC クラス](../../mfc/reference/adding-an-mfc-class.md)   
 [メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)   
 [インターフェイスの実装](../../ide/implementing-an-interface-visual-cpp.md)   
 [ウィザードでサポートされるその他の言語](../../ide/wizard-support-for-other-languages.md)