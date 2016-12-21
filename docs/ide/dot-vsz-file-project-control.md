---
title: ".vsz ファイル (プロジェクト コントロール) | Microsoft Docs"
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
  - ".vsz ファイル"
  - "カスタム ウィザード, .vsz ファイル"
  - "カスタム ウィザード, プロジェクト コントロール ファイル"
  - "ファイル [C++], 作成 (カスタム ウィザードで)"
  - "vsz ファイル"
ms.assetid: b8678fee-6795-46d1-9338-48b22d5e9207
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# .vsz ファイル (プロジェクト コントロール)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ウィザードは .vsz ファイルで開始します。  .vsz ファイルとは、呼び出されるウィザードとそのウィザードに渡す情報を指定するテキスト ファイルです。  このファイルには、2 行のヘッダーの後に、ウィザードに渡すさまざまな省略可能パラメーターが指定されています。  省略可能なパラメーターのリストについては、「[ウィザードの .vsz ファイルのカスタム パラメーター](../ide/custom-parameters-in-the-wizard-dot-vsz-file.md)」を参照してください。  
  
 .vsz ファイルのヘッダーの例を次に示します。  
  
```  
VSWIZARD 7.0  
Wizard=VsWizard.VsWizardEngine.10.0  
Param="WIZARD_NAME = My AppWizard"  
```  
  
-   ヘッダーの最初の行は、テンプレート ファイル形式のバージョン番号を指定します。  この番号として、`6.0`、`7.0`、または `7.1` を指定できます。  それ以外の番号は無効です。無効な番号を使用すると、"無効な形式" エラーが発生します。  
  
-   2 行目は、**Wizard** 変数を Visual Studio で一緒に作成されるウィザードの ProgID に設定します。  ProgID は、`VsWizard.VsWizardEngine.10.0` のような、CLSID の文字列形式です。  
  
     ウィザードにユーザー インターフェイスがある場合は、ウィザードが <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI> を実装するように ProgID で自動的に指定されます。  既定では、このインターフェイスのメソッドは、プロジェクトの [.htm ファイル](../ide/html-files.md)で使用されます。  .htm ファイルでこのインターフェイスのメソッドを使用すると、ウィザードの動作を変更できます。  詳細については、<xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI> のコクラスである <xref:Microsoft.VisualStudio.VsWizard.VCWizCtl> に関するトピックを参照してください。  
  
-   この 2 行の後には、省略可能なパラメーターのリストが指定されます。これにより、.vsz ファイルはその他のカスタム パラメーターをウィザードに渡すことができます。  値は、ウィザード コントロールの <xref:Microsoft.VisualStudio.VsWizard.VsWizardClass.Execute%2A> メソッドで、バリアント型の配列の文字列要素として渡されます。  既定では、ユーザー インターフェイスがあるウィザードは、次の既定パラメーターを生成します。  
  
    ```  
    Param="START_PATH = <path to the wizard>"  
    Param="HTML_PATH = <path to the wizard's HTML file>"  
    Param="TEMPLATES_PATH = <path to the wizard's template file>"  
    Param="SCRIPT_PATH = <path to the wizard's script files>"  
    Param="IMAGES_PATH = <path to the wizard's images>"  
    ```  
  
     ウィザードにユーザー インターフェイスがない場合は、`IMAGES_PATH` パラメーターではなく、次のパラメーターが含まれます。  
  
    ```  
    Param="WIZARD_UI = FALSE"  
    Param="SOURCE_FILTER = txt"  
    ```  
  
-   .vsz ファイルには、[Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md) ファイルにある関数を指定する次のパラメーターを含めることができます。  
  
    ```  
    Param="PREPROCESS_FUNCTION = CanAddATLClass"  
    Param="PREPROCESS_FUNCTION = CanAddMFCClass"  
    Param="PREPROCESS_FUNCTION = CanAddClass"  
    ```  
  
 [CanAddATLClass](../ide/canaddatlclass.md)、[CanAddMFCClass](../ide/canaddmfcclass.md)、および [CanAddClass](../ide/canaddclass.md) の各関数は、[Visual C\+\+ コード モデル](http://msdn.microsoft.com/ja-jp/dd6452c2-1054-44a1-b0eb-639a94a1216b)が使用できることを確認するためにウィザードによって呼び出されます。  いずれかの関数が **false** を返すと、ウィザードは起動しません。  
  
 .vsz ファイルを vcprojects ディレクトリに格納することによって、Visual Studio の **\[新しいプロジェクト\]** ダイアログ ボックスのテンプレート ペインにウィザードを追加できます。  既定では、カスタム ウィザードによって .vsz ファイルがこのディレクトリに作成されます。  
  
> [!NOTE]
>  ウィザードのファイルとディレクトリを削除する場合は、プロジェクトの .vsz ファイル、.vsdir ファイル、および .ico ファイルを vcprojects ディレクトリから削除する必要もあります。  
  
## 参照  
 [ウィザード用に作成されるファイル](../ide/files-created-for-your-wizard.md)   
 [カスタム ウィザード](../ide/custom-wizard.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [Visual C\+\+ Wizard Model](http://msdn.microsoft.com/ja-jp/159395ac-33c7-47bf-ad42-4e1435ddc758)   
 [Adding Wizards to the Add Item and New Project Dialog Boxes by Using .Vsdir Files](../Topic/Adding%20Wizards%20to%20the%20Add%20Item%20and%20New%20Project%20Dialog%20Boxes%20by%20Using%20.Vsdir%20Files.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)