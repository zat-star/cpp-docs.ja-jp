---
title: "ウィザードをデザインする手順 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "カスタム ウィザード, デザイン"
ms.assetid: dc22746b-99e3-4569-a8b4-b3d7cbabf8f2
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ウィザードをデザインする手順
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ウィザードを使用すると、共通のプロジェクト初期ファイルを作成および構成できます。  プロジェクトの場合と同様に、ウィザードの作成にも計画が必要です。  Visual C\+\+ のカスタム ウィザードについて理解し、独自のプロジェクトに適用する方法の 1 つを次に示します。  
  
1.  Visual Studio に用意されている[カスタム ウィザードのサンプル](http://msdn.microsoft.com/ja-jp/6afa2143-062c-4a68-81ca-66cbf4b95261)をチェックします。  
  
2.  ウィザードで作成するプロジェクトの種類について、基本事項を指定します。  アプリケーション構築と同様に、このプロセスには多数の人がかかわって、何回も繰り返されることがあります。  
  
3.  Visual C\+\+ の[カスタム ウィザード](../ide/creating-a-custom-wizard.md)でプロジェクトを作成し、ユーザー インターフェイスとページ番号のオプションを指定します。  
  
    > [!NOTE]
    >  ユーザー インターフェイスを指定しない場合、つまりカスタム ウィザードの [&#91;アプリケーションの設定&#93; \(&#91;カスタム ウィザード&#93;\)](../Topic/Application%20Settings,%20Custom%20Wizard.md) の \[ユーザー インターフェイス\] をオフにする場合は、ウィザードでカスタム パラメーター WIZARD\_UI\=**FALSE** が設定され、ユーザー入力や .htm ファイルを含まないプロジェクト テンプレート ファイルが作成されます。  このため、ページ番号も指定しません。  詳細については、「[.vsz ファイル \(プロジェクト コントロール\)](../ide/dot-vsz-file-project-control.md)」を参照してください。  
  
4.  カスタム ウィザードで作成された[基本のプロジェクトをチェック](../ide/examining-the-basic-wizard-project.md)します。  
  
5.  ウィザードにユーザー インターフェイスがある場合は、ウィザードを実行して、[カスタム ウィザードのしくみをさらに詳しく調べて](../Topic/Examining%20the%20Mechanics%20of%20a%20Wizard.md)ください。  
  
6.  [基本のウィザードをカスタマイズします](../ide/customizing-your-wizard.md)。  
  
7.  [状況依存のヘルプを追加します](../ide/providing-context-sensitive-help.md)。  
  
8.  JScript コードと HTML コードのための[エラー処理を指定します](../ide/handling-errors-in-wizards.md)。  
  
9. ウィザードをビルドしてテストします。  
  
10. ウィザードをデバッグします。  詳細については、「[スクリプトと Web アプリケーションのデバッグ](../Topic/Debugging%20Web%20Applications%20and%20Script.md)」を参照してください。  
  
    > [!NOTE]
    >  JScript をデバッグするときは、ネイティブ コードでの混合モード デバッグを実行できません。  
  
## 参照  
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [カスタム ウィザード](../ide/custom-wizard.md)   
 [ウィザード用に作成されるファイル](../ide/files-created-for-your-wizard.md)