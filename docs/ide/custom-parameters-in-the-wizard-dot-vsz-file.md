---
title: "ウィザードの .vsz ファイルのカスタム パラメーター | Microsoft Docs"
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
  - "ABSOLUTE_PATH マクロ"
  - "カスタム ウィザード, .vsz ファイル"
  - "HTML_FILTER マクロ"
  - "HTML_PATH マクロ"
  - "IMAGE_FILTER マクロ"
  - "IMAGES_PATH マクロ"
  - "MISC_FILTER マクロ"
  - "PRODUCT マクロ"
  - "PRODUCT_INSTALLATION_DIR マクロ"
  - "PROJECT_TEMPLATE_NAME マクロ"
  - "PROJECT_TEMPLATE_PATH マクロ"
  - "RELATIVE_PATH マクロ"
  - "SCRIPT_COMMON_PATH マクロ"
  - "SCRIPT_FILTER マクロ"
  - "SCRIPT_PATH マクロ"
  - "START_PATH マクロ"
  - "TEMPLATE_FILTER マクロ"
  - "TEMPLATES_PATH マクロ"
  - "WIZARD_NAME マクロ"
  - "WIZARD_UI マクロ"
ms.assetid: 560dd5c0-7cff-4974-b856-5ca25b0669b8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ウィザードの .vsz ファイルのカスタム パラメーター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

.vsz ファイルの最初の 2 行では、ウィザードのバージョンと、一緒に作成するウィザードの ProgID または CLSID が指定されます。  .vsz ファイルには、省略可能なコンテキスト パラメーターやカスタム パラメーターを含めることもできます。これらのパラメーターは、HTML シンボル セクションで指定されたシンボルと共に、シンボル テーブルに追加されます。  
  
 <xref:Microsoft.VisualStudio.VsWizard.VsWizardClass.Execute%2A> メソッドによってウィザードが表示されます。このメソッドでは、.vsz ファイルで定義されたコンテキスト パラメーターやカスタム パラメーターの配列をパラメーターとして使用します。  
  
 一般的に使用されるシンボルを次に示します。これらのシンボルは、[.vsz ファイル](../ide/dot-vsz-file-project-control.md)または .htm ファイルにカスタム パラメーターとして指定され、ウィザードの HTML ファイル、スクリプト ファイル、またはテンプレート ファイルで使用できます。  
  
## 使用例  
 次の例の .vsz ファイル エントリが示すように、MyProjWiz という名前のウィザードにはユーザー インターフェイスがあります。  
  
```  
VSWIZARD 7.0  
Wizard=VsWizard.VsWizardEngine  
Param="WIZARD_NAME = MyProjWiz"  
Param="WIZARD_UI = TRUE"  
```  
  
### ウィザードの .vsz ファイルのカスタム パラメーターのシンボル  
  
|シンボル|定義|  
|----------|--------|  
|ABSOLUTE\_PATH|ウィザード ファイルの場所です。|  
|HTML\_FILTER|.vsz ファイル内に指定されています。  **ソリューション エクスプローラー**の \[HTML ファイル\] フォルダーに入れるファイルの種類です。  通常は "htm" に指定されます。|  
|HTML\_PATH|.vsz ファイル内に指定されています。  ウィザードの [HTML ファイル](../ide/html-files.md)の場所です。  既定では、START\_PATH\\HTML\\*LANGUAGE* \(*LANGUAGE* はシステム レジストリで指定されているロケール\) です。 **Note:**  別の言語を指定するには、\<LangID\> を HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\7.0\\General\\UILanguage の 10 進値に設定します。  詳細については、「[複数言語へのウィザードのローカライズ](../ide/localizing-a-wizard-to-multiple-languages.md)」を参照してください。  言語に対応する 10 進値の一覧については、「[ウィザードでサポートされるその他の言語](../ide/wizard-support-for-other-languages.md)」を参照してください。|  
|IMAGE\_FILTER|.vsz ファイル内に指定されています。  ソリューション エクスプローラーの \[イメージ ファイル\] フォルダーに入れるファイルの種類です。  通常は "bmp;gif" に指定されます。|  
|IMAGES\_PATH|.vsz ファイル内に指定されています。  html ファイルで使用されるイメージ ファイルの場所です。  既定では、START\_PATH\\Images です。|  
|MISC\_FILTER|.vsz ファイル内に指定されています。  ソリューション エクスプローラーの \[その他\] フォルダーに入れるファイルの種類です。  通常は "vsz;vsdir;ico;vcproj;csproj;css;inf" に指定されます。|  
|PRODUCT|既定では、Visual C\+\+ に設定されます。ただし、この値を Visual Basic に設定して Visual Basic のウィザードを作成することもできます。|  
|PRODUCT\_INSTALLATION\_DIR|レジストリ HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\7.0\\Setup\\\<Product\>\\ の ProductDir に設定されるディレクトリです。|  
|PROJECT\_TEMPLATE\_NAME|.vsz ファイル内に指定されています。  ウィザードでプロジェクトの作成に使用するプロジェクト テンプレート ファイルです。  通常は "txt" に指定されます。|  
|PROJECT\_TEMPLATE\_PATH|プロジェクトの[テンプレート ファイル](../ide/template-files.md)を含むディレクトリです。  Visual C\+\+ の場合の既定値は PRODUCT\_INSTALLATION\_DIR\\VCWizards です。|  
|RELATIVE\_PATH|ABSOLUTE\_PATH が見つからない場合は、RELATIVE\_PATH が使用されます。  これは、PRODUCT\_INSTALLATION\_DIR に対する相対パスです。  Visual C\+\+ の場合、RELATIVE\_PATH は PRODUCT\_INSTALLATION\_DIR\\VCWizards です。|  
|SCRIPT\_COMMON\_PATH|PRODUCT\_INSTALLATION\_DIR に対する相対的なディレクトリ名です。このディレクトリには共通のスクリプト ファイルが保存されます。  たとえば、Visual C\+\+ の場合は VCWizards です。|  
|SCRIPT\_FILTER|.vsz ファイル内に指定されています。  ソリューション エクスプローラーの \[スクリプト ファイル\] フォルダーに入れるファイルの種類です。  通常は "js" \(JScript\) または "vbs" \(VBScript\) に指定されます。|  
|SCRIPT\_PATH|ウィザードの [JScript ファイル](../ide/jscript-file.md)の場所です。  既定では、START\_PATH\\Scripts です。|  
|START\_PATH|.vsz ファイル内に指定されています。  ユーザーは設定しません。RELATIVE\_PATH または ABSOLUTE\_PATH を識別するために、内部的に使用されます。  ウィザード名 \(WIZARD\_NAME\) がこの値の後に付けられます。|  
|TEMPLATE\_FILTER|.vsz ファイル内に指定されています。  ソリューション エクスプローラーの \[テンプレート ファイル\] フォルダーに入れるファイルの種類です。  通常は "txt" に指定されます。|  
|TEMPLATES\_PATH|.vsz ファイル内に指定されています。  ウィザードのテンプレート ファイルの場所です。  既定では、START\_PATH\\Templates\\\<LangID\> です。 **Note:**  LangID の詳細については、HTML\_PATH を参照してください。|  
|WIZARD\_NAME|ウィザード名を指定します。  .vsz にあり、ほかのシンボルで使用されます。|  
|WIZARD\_UI|.vsz ファイル内に指定されています。  ウィザードにユーザー インターフェイスを含めるかどうかを指定するブール値です。  ユーザー インターフェイスを含める場合は **TRUE**、含めない場合は **FALSE** を指定します。|  
  
## 参照  
 <xref:EnvDTE.IDTWizard.Execute%2A>   
 [ウィザード用に作成されるファイル](../ide/files-created-for-your-wizard.md)   
 [カスタム ウィザード](../ide/custom-wizard.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)