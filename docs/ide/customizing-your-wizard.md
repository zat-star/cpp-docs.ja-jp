---
title: "ウィザードのカスタマイズ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "カスタム ウィザード"
  - "カスタム ウィザード, 作成 (Visual C++ プロジェクトでの)"
ms.assetid: a3ff1c81-3eef-41e7-a6bc-2f98e4bf423f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ウィザードのカスタマイズ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[カスタム ウィザード](../Topic/Application%20Settings,%20Custom%20Wizard.md)で作成したウィザードをカスタマイズするときは、次に示す作業を実行する必要があります。  
  
-   .vsz ファイルに、ウィザードの動作に必要なすべてのカスタム パラメーターを指定します。  詳細については、「[.vsz ファイル \(プロジェクト コントロール\)](../ide/dot-vsz-file-project-control.md)」および「[ウィザードの .vsz ファイルのカスタム パラメーター](../ide/custom-parameters-in-the-wizard-dot-vsz-file.md)」を参照してください。  
  
     ウィザードをさまざまな言語にローカライズする場合は、それらの言語のパラメーターを .vsz ファイルに追加します。  詳細については、「[複数言語へのウィザードのローカライズ](../ide/localizing-a-wizard-to-multiple-languages.md)」を参照してください。  
  
-   [テンプレート ファイル](../ide/template-files.md)と [Templates.inf](../Topic/Templates.inf%20File.md) をカスタマイズして、ユーザーの選択に対するディレクティブを指定します。  
  
-   [Default.js ファイル](../ide/jscript-file.md)をカスタマイズして、ウィザードに追加するその他の特別な処理を指定します。  独自の関数を作成できます。また、[Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md) にある関数を使用できます。  
  
-   HTML ユーザー インターフェイスで使用するアイコンなどのイメージをデザインします。  
  
-   HTML ユーザー インターフェイスをデザインします。  
  
-   ウィザードで使用するボタン、コントロール、テキスト ボックスなどの要素に対応するシンボルを、HTML シンボル テーブルに追加します。  
  
     カスタム ウィザードによって提供される HTML の抜粋を次に示します。  
  
    ```  
    <SYMBOL NAME="WIZARD_DIALOG_TITLE" TYPE=text VALUE="MyCustomWiz">  
          </SYMBOL>  
    <SYMBOL NAME="SAMPLE_CHECKBOX" TYPE=checkbox VALUE=true>  
          </SYMBOL>  
    ```  
  
     MyCustomWiz という名前のこのウィザードでは、既定でオンになっているチェック ボックスが表示されます。  
  
-   HTML ファイルの `<SCRIPT LANGUAGE="JSCRIPT">` セクションで、JScript 関数呼び出しを追加し、Visual Studio のオブジェクト モデルにアクセスしてウィザードの動作をカスタマイズします。  これらの関数は、次のように `window.external` を使用して呼び出す必要があります。  
  
    ```  
    window.external.AddSymbol("MAIN_FRAME_DEFAULT_STYLES", true);  
    window.external.AddSymbol("MAIN_FRAME_STYLE_FLAGS", "");  
    ```  
  
    > [!NOTE]
    >  [Automation and Extensibility for Visual Studio](../Topic/Automation%20and%20Extensibility%20for%20Visual%20Studio.md)、[Visual C\+\+ コード モデル](http://msdn.microsoft.com/ja-jp/dd6452c2-1054-44a1-b0eb-639a94a1216b)、[プロジェクト モデル](http://msdn.microsoft.com/ja-jp/06c1bbd9-4c79-4f97-ad6d-2b1dea8ecd1f)、および[ウィザード モデル](http://msdn.microsoft.com/ja-jp/159395ac-33c7-47bf-ad42-4e1435ddc758)を介して公開されるメソッド、プロパティ、およびイベントを使用すると、JScript ファイルと .htm ファイルの両方で、ウィザード プロジェクトの作成からビルドまでのすべての段階をプログラムで管理できます。  
  
-   必要に応じて、.vsz ファイルとほかのすべてのテンプレートの情報をシェルが認識できるように、[.vsdir ファイル](../Topic/Adding%20Wizards%20to%20the%20Add%20Item%20and%20New%20Project%20Dialog%20Boxes%20by%20Using%20.Vsdir%20Files.md)をカスタマイズします。  たとえば、アイコン リソース ID、フラグ、ローカライズされた名前などを指定します。  
  
-   ウィザードをローカライズする必要があるすべての言語で、.htm ファイルとテンプレート ファイルを作成します。  作成したファイルを適切なプロジェクト ディレクトリに追加します。  
  
-   ウィザード用に[状況依存のヘルプを用意](../ide/providing-context-sensitive-help.md)します。  
  
## 参照  
 [カスタム ウィザード](../ide/custom-wizard.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードをデザインする手順](../ide/steps-to-designing-a-wizard.md)   
 [ウィザード用に作成されるファイル](../ide/files-created-for-your-wizard.md)   
 [状況依存のヘルプの指定](../ide/providing-context-sensitive-help.md)   
 [ウィザードでのエラー処理](../ide/handling-errors-in-wizards.md)