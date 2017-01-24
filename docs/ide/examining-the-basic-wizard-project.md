---
title: "基本のウィザード プロジェクトのチェック | Microsoft Docs"
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
  - "カスタム ウィザード, ファイル (作成された)"
  - "カスタム ウィザード, ウィザード プロジェクト"
ms.assetid: c6423e3c-ddb0-43e0-b8e5-9e3a98a7908c
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 基本のウィザード プロジェクトのチェック
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[カスタム ウィザード](../ide/creating-a-custom-wizard.md)を使用して基本プロジェクトを作成したら、作成されたファイルをチェックします。  
  
1.  **ソリューション エクスプローラー**でプロジェクトを展開し、ウィザードがプロジェクト用に作成した[ファイル](../ide/files-created-for-your-wizard.md)をチェックします。  
  
2.  Default.js をダブルクリックすると、プロジェクトの [JScript ファイル](../ide/jscript-file.md)がコード エディターで開きます。  このファイルには、ユーザーがウィザードの \[完了\] をクリックしたときにプロジェクトを作成する JScript 関数が含まれています。  このファイル内の関数と TODO コメントを確認します。  
  
3.  プロジェクトにユーザー インターフェイスがある場合は、[&#91;HTML ファイル&#93;](../ide/html-files.md) というラベルのフォルダーを調べて、カスタム ウィザードの [&#91;アプリケーションの設定&#93;](../Topic/Application%20Settings,%20Custom%20Wizard.md) ページで指定した数の .htm ファイルがあるかどうかを確認します。  Default.htm をダブルクリックすると、プロジェクトのメイン HTML ページが [HTML デザイナー](../Topic/HTML%20Designer.md)で開きます。  HTML は、[Design View](../Topic/Design%20View1.md)や HTML ビューに [HTML マークアップ](http://msdn.microsoft.com/ja-jp/7bb90672-b36a-4cf9-9bbc-677c9b956318)として表示できます。  HTML マークアップ表示に切り替えて、HTML マークアップを確認します。  HTML ビューの編集ウィンドウの右上隅にあるイベントのドロップダウン リスト横の \[スクリプトのみ表示\] ボタンをクリックし、.htm ファイル内の JScript をチェックします。  既定では、このファイルには、ウィザードの初期化と読み込みを行う JScript 関数が含まれています。また、**IVCWizCtrlUI** インターフェイスの既定の動作が指定されています。  詳細については、コクラスの <xref:Microsoft.VisualStudio.VsWizard.VCWizCtl> オブジェクトに関するトピックを参照してください。  
  
4.  ウィザード プロジェクトを保存して閉じます。  
  
5.  Visual Studio の **\[新しいプロジェクト\]** ダイアログ ボックスを開き、ウィザードのアイコンを確認します。  アイコンをダブルクリックすると、作成したウィザードが表示されます。  カスタム ウィザードで作成された基本のウィザード ページをチェックできます。  最初のページには、いくつかの HTML コントロールのサンプルと、標準の \[完了\]、\[キャンセル\]、\[ヘルプ\] の各ボタンがあります。  
  
6.  \[完了\] をクリックすると、ウィザードで新しいプロジェクトがビルドされます。  既定では、ウィザードにより、ReadMe.txt と Sample.txt の 2 つのテキスト ファイルが作成されます。  これらのファイルは、ウィザードで作成されたプロジェクトについて説明します。  このプロジェクトを閉じて、再度ウィザード プロジェクトを開きます。  
  
7.  「[ウィザードのしくみの検証](../Topic/Examining%20the%20Mechanics%20of%20a%20Wizard.md)」では、ウィザードの実行時における Visual Studio 環境と Visual C\+\+ ウィザード エンジンによるプロジェクトの作成方法について、より詳細に説明しています。  
  
 これで、[カスタム ウィザードのカスタマイズ](../ide/customizing-your-wizard.md)に進むことができます。  
  
## 参照  
 [カスタム ウィザード](../ide/custom-wizard.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードをデザインする手順](../ide/steps-to-designing-a-wizard.md)   
 [ウィザード用に作成されるファイル](../ide/files-created-for-your-wizard.md)   
 [状況依存のヘルプの指定](../ide/providing-context-sensitive-help.md)   
 [ウィザードのカスタマイズ](../ide/customizing-your-wizard.md)