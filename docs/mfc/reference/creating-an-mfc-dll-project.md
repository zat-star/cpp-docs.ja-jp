---
title: "MFC DLL プロジェクトの作成 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfcdll.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL [C++], 作成"
  - "DLL [C++], MFC"
  - "MFC DLL [C++], 作成 (プロジェクトを)"
  - "プロジェクト [C++], 作成"
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# MFC DLL プロジェクトの作成
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC DLL とは、複数のアプリケーションで同時に利用できる関数の共有ライブラリとして機能する、バイナリ ファイルです。  MFC DLL プロジェクトを作成する最も簡単な方法は、MFC DLL ウィザードを使用する方法です。  
  
> [!NOTE]
>  IDE に表示される機能は、有効にされている設定やエディションに依存し、ヘルプに記載されている内容とは異なる場合があります。  設定を変更するには、**\[ツール\]** メニューの **\[設定のインポートとエクスポート\]** をクリックします。  詳細については、「[Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ja-jp/22c4debb-4e31-47a8-8f19-16f328d7dcd3)」を参照してください。  
  
### MFC DLL ウィザードを使用して MFC DLL プロジェクトを作成するには  
  
1.  「[Visual C\+\+ のアプリケーション ウィザードを使用したプロジェクトの作成](../../ide/creating-desktop-projects-by-using-application-wizards.md)」の手順に従います。  
  
 **メモ** MFC DLL ウィザードを開くには、**\[新しいプロジェクト\]** ダイアログ ボックスで、\[テンプレート\] ペインの `MFC DLL` アイコンをクリックします。  
  
1.  [MFC DLL ウィザード](../../mfc/reference/mfc-dll-wizard.md)の [&#91;アプリケーションの設定&#93;](../../mfc/reference/application-settings-mfc-dll-wizard.md) ページを使用して、アプリケーション設定を定義します。  
  
    > [!NOTE]
    >  ウィザードの既定の設定を使用する場合は、この手順を省略します。  
  
2.  **\[完了\]** をクリックしてウィザードを閉じ、**ソリューション エクスプローラー**で新しいプロジェクトを開きます。  
  
 作成したプロジェクトのファイルは、ソリューション エクスプローラーで確認できます。  ウィザードでプロジェクト用に作成されるファイルの詳細については、プロジェクトが生成する ReadMe.txt ファイルを参照してください。  ファイルの種類の詳細については、「[Visual C\+\+ プロジェクトに対して作成されるファイルの種類](../../ide/file-types-created-for-visual-cpp-projects.md)」を参照してください。  
  
## 参照  
 [Visual C\+\+ プロジェクトの種類](../Topic/Debugging%20Preparation:%20Visual%20C++%20Project%20Types.md)   
 [コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [プロパティ ページ](../../ide/property-pages-visual-cpp.md)   
 [Deploying Applications](http://msdn.microsoft.com/ja-jp/4ff8881d-0daf-47e7-bfe7-774c625031b4)