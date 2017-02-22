---
title: "Grouping Radio Buttons on a Dialog Box | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.dialog.grouping"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "member variables, adding to radio button groups"
  - "variables, dialog box control member variables"
  - "dialog box controls, grouping radio buttons"
  - "grouping controls"
  - "radio buttons, grouping on dialog boxes"
ms.assetid: 3cc43f9e-56c8-4faa-9930-ce81733c69de
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Grouping Radio Buttons on a Dialog Box
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ダイアログ ボックスにラジオ ボタン群を追加するときには、これをグループとして扱ってください。そのためには、グループの最初のボタンの \[プロパティ\] ウィンドウで \[グループ\] プロパティを設定します。 そのラジオ ボタンのコントロール ID が[メンバー変数の追加ウィザード](../ide/add-member-variable-wizard.md)に表示され、ラジオ ボタンのグループのメンバー変数を追加できるようになります。  
  
 1 つのダイアログ ボックスにラジオ ボタンの複数のグループを設定できます。各グループは次の手順を使用して追加する必要があります。  
  
### ラジオ ボタンのグループをダイアログ ボックスに追加するには  
  
1.  [&#91;ツールボックス&#93; ウィンドウ](../Topic/Toolbox.md)でラジオ ボタン コントロールを選び、ダイアログ ボックス内でそのコントロールを配置する位置をクリックします。  
  
2.  手順 1.を繰り返して、必要な数のラジオ ボタンを追加します。 グループのラジオ ボタンがタブ オーダーで連続していることを確認します \(詳しくは「[コントロールのタブ オーダーの変更](../mfc/changing-the-tab-order-of-controls.md)」をご覧ください\)。  
  
3.  [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)で、タブ オーダーが*最初*のラジオ ボタンの **\[グループ\]** プロパティを **\[True\]** に設定します。  
  
     **\[グループ\]** プロパティを **\[True\]** に変更すると、リソース スクリプトのダイアログ オブジェクト内でそのボタンのエントリに WS\_GROUP スタイルが追加されます。このため、ユーザーはボタン グループのラジオ ボタンを一度に 1 つしか選べなくなります \(ユーザーがラジオ ボタンを 1 つクリックすると、グループの残りのボタンはクリアされます\)。  
  
    > [!NOTE]
    >  **\[グループ\]** プロパティを **\[True\]** に設定する必要があるのは、グループ内の最初のラジオ ボタンだけです。 ボタン グループに属さないその他のコントロールがある場合は、*グループ以外の*最初のコントロールの **\[グループ\]** プロパティも同様に **\[True\]** に設定します。 Ctrl キーを押しながら D キーを押してタブ オーダーを表示すると、グループ外の最初のコントロールをすばやく識別できます。  
  
### ラジオ ボタン グループのメンバー変数を追加するには  
  
1.  タブ オーダーの最初のラジオ ボタン コントロール \(主要なコントロールであり、**\[グループ\]** プロパティが \[True\] に設定されている\) を右クリックします。  
  
2.  ショートカット メニューの **\[変数の追加\]** を選びます。  
  
3.  [&#91;メンバー変数の追加ウィザード&#93;](../ide/add-member-variable-wizard.md) で、**\[コントロール変数\]** チェック ボックスをオンにして、次に **\[値\]** ラジオ ボタンを選びます。  
  
4.  **\[変数名\]** ボックスに、新しいメンバー変数の名前を入力します。  
  
5.  **\[変数の型\]** リスト ボックスで、**\[int\]** を選ぶか、または**「int」**と入力します。  
  
6.  これで、コードを変更し、表示したときに選ばれているラジオ ボタンを指定できます。 たとえば、m\_radioBox1 \= 0 の場合は、グループの最初のラジオ ボタンが選ばれます。  
  
 マネージ プロジェクトにリソースを追加する方法については、『*.NET Framework 開発者ガイド*』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」をご覧ください。  
  
 要件  
  
 Win32  
  
## 参照  
 [Arrangement of Controls on Dialog Boxes](../mfc/arrangement-of-controls-on-dialog-boxes.md)   
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [コントロール](../mfc/controls-mfc.md)