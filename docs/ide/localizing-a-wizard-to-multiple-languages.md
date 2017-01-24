---
title: "複数言語へのウィザードのローカライズ | Microsoft Docs"
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
  - "カスタム ウィザード, ローカライズ"
  - "グローバリゼーション [C++], ウィザード"
  - "ローカリゼーション [C++], ウィザード"
  - "ウィザード [C++], ローカライズ"
ms.assetid: 879885c2-fafd-44fd-8032-bf0c301f4f45
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 複数言語へのウィザードのローカライズ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio でサポートされているすべての言語でウィザードを作成できます。  既定では、Visual Studio をインストールすると、レジストリからロケールが識別され、そのロケールに対応する適切なテンプレートが指定されます。  
  
 Visual Studio では、言語 ID を使用して、ウィザードが必要とする言語サポートを識別します。  既定では、言語 ID はレジストリ エントリ HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\7.0\\General\\UILanguage の 10 進値に設定されています。  ウィザードで言語エントリを検出できない場合は、既定の英語 \(1033\) になります。  
  
> [!NOTE]
>  言語に対応する 10 進値の一覧については、「[ウィザードでサポートされるその他の言語](../ide/wizard-support-for-other-languages.md)」を参照してください。  
  
 言語 ID は、[HTML ファイル](../ide/html-files.md)と[テンプレート ファイル](../ide/template-files.md)があるパスの .[vsz ファイル](../Topic/Configuring%20.Vsz%20Files%20to%20Start%20Wizards.md)に、カスタム パラメーターとして指定されます。  
  
 .htm ファイルを用意する言語ごとにパスを指定する必要があります。  
  
## 使用例  
 英語 \(1033\)、日本語 \(1041\)、およびドイツ語 \(1031\) の HTML を用意する場合は、.vsz ファイルに次のカスタム パラメーターを設定します。  
  
```  
Param="START_PATH\HTML\1033"  
Param="START_PATH\HTML\1041"  
Param="START_PATH\HTML\1031"  
Param="START_PATH\Templates\1033"  
Param="START_PATH\Templates\1041"  
Param="START_PATH\Templates\1031"  
```  
  
 これらのカスタム パラメーターを設定すると、ウィザードのディレクトリ構造は次のようになります。  
  
```  
MyWizard1  
   HTML  
      1033  
         default.htm  
         myEnglishHTML.htm  
      1041  
         default.htm  
         myJapaneseHTML.htm  
      1031  
         default.htm  
         myGermanHTML.htm  
   Templates  
      1033  
         stdafx.h  
         stdafx.cpp  
      1041  
         stdafx.h  
         stdafx.cpp  
      1031  
         stdafx.h  
         stdafx.cpp  
   Images  
      HtmlPage1.bmp  
      HtmlPage2.jpg  
   Scripts  
      Default.js  
```  
  
## 参照  
 [ウィザード用に作成されるファイル](../ide/files-created-for-your-wizard.md)   
 [カスタム ウィザード](../ide/custom-wizard.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)   
 [ウィザードの .vsz ファイルのカスタム パラメーター](../ide/custom-parameters-in-the-wizard-dot-vsz-file.md)