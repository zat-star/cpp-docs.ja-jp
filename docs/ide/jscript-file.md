---
title: "JScript ファイル | Microsoft Docs"
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
  - "AddConfig メソッド"
  - "AddFilesToCustomProj メソッド"
  - "AddFilters メソッド"
  - "Common.js ファイル"
  - "CreateCustomInfFile メソッド"
  - "CreateCustomProject メソッド"
  - "カスタム ウィザード, アクセス (ウィザード オブジェクト モデルへの)"
  - "カスタム ウィザード, JScript ファイル"
  - "デバッグ [JScript], 有効化 (スクリプト デバッグを)"
  - "デバッグ [JScript], JScript ファイル"
  - "デバッグ (スクリプトの)"
  - "デバッグ (スクリプトの), 有効化 (スクリプト デバッグを)"
  - "Default.js ファイル"
  - "DelFile メソッド"
  - "ファイル [C++], 作成 (カスタム ウィザードで)"
  - "GetTargetName メソッド"
  - "JScript ファイル"
  - "OnFinish メソッド"
  - "PchSettings メソッド"
ms.assetid: 7841a09e-2dd2-4f1a-a13a-39ac53f24315
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# JScript ファイル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[カスタム ウィザード](../ide/custom-wizard.md)はスクリプト エンジンにアクセスし、プロジェクトごとに Default.js という JScript ファイルを作成します。  また、[Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md) もインクルードされます。  これらのファイルには JScript 関数が含まれています。JScript 関数を使用すると、Visual Studio や Visual C\+\+ のオブジェクト モデルにアクセスして、ウィザードをカスタマイズできます。  これらのオブジェクト モデルの一覧については、「[ウィザードのデザイン](../ide/designing-a-wizard.md)」を参照してください。ウィザード プロジェクトの Default.js ファイルには、独自の関数を追加できます。  JScript ファイルからウィザード オブジェクト モデルや環境モデルのプロパティとメソッドにアクセスするには、オブジェクト モデル アイテムの前にそれぞれ "wizard." および "dte." を付けます。  
  
 次に例を示します。  
  
```  
function CreateCustomProject(strProjectName, strProjectPath)  
{  
   try  
   {  
      var strProjTemplatePath = wizard.FindSymbol('PROJECT_TEMPLATE_PATH');  
var strProjTemplate = '';  
      strProjTemplate = strProjTemplatePath + '\\default.vcproj';  
  
      var Solution = dte.Solution;  
      var strSolutionName = "";  
      if (wizard.FindSymbol("CLOSE_SOLUTION"))  
...  
```  
  
 [カスタム ウィザード](../ide/custom-wizard.md)の \[完了\] をクリックすると、ウィザードは、ソリューション エクスプローラーの \[スクリプト ファイル\] フォルダーにある Default.js ファイルを読み込みます。  ユーザーがウィザードの \[完了\] をクリックすると、この JScript ファイルがプロジェクトを作成し、テンプレートをレンダリングして、ソリューションに追加します。  
  
 既定では、プロジェクトの Default.js ファイルには次の関数が含まれています。  
  
|関数名|Description|  
|---------|-----------------|  
|**AddConfig**|プロジェクトの構成を追加します。  コンパイラとリンカーの設定を指定できます。|  
|**AddFilesToCustomProj**|ユーザーが \[完了\] をクリックしたときに、指定されたファイルをプロジェクトに追加します。|  
|**AddFilters**|ユーザーが \[完了\] をクリックしたときに、指定されたソース フィルターをプロジェクトに追加します。|  
|**CreateCustomProject**|ユーザーが \[完了\] をクリックしたときに、指定された場所にプロジェクトを作成します。|  
|**CreateCustomInfFile**|プロジェクトの [Templates.inf ファイル](../Topic/Templates.inf%20File.md)を作成します。|  
|**DelFile**|指定されたファイルを削除します。|  
|**GetTargetName**|指定されたファイルの名前を取得します。|  
|**OnFinish**|ユーザーが \[完了\] をクリックしたときにウィザードによって呼び出され、プロジェクトを作成し、ファイルとフィルターを追加し、テンプレートをレンダリングし、構成を設定します。|  
|**PchSettings**|プリコンパイル済みヘッダーを設定します。  詳細については、「JScript ファイル」の「[SetCommonPchSettings](../ide/setcommonpchsettings.md)」を参照してください。|  
  
 各ウィザードには固有の Default.js ファイルがあります。このファイルには TODO コメントが含まれており、ファイルをカスタマイズする必要がある箇所を識別するために役立ちます。  
  
 Visual C\+\+ には [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md) もあります。このファイルはすべてのウィザードで共有されるファイルであり、作成するウィザード プロジェクトにもインクルードされます。  Common.js の関数を使用できます。  
  
> [!NOTE]
>  Common.js には、各関数とそのパラメーターの説明が含まれています。  詳細については、Common.js のコメントを参照してください。  
  
 複数のウィザード プロジェクトで共有する関数がある場合は、その関数を Common.js に追加できます。  独自の Common.js を作成して共通パスに保存し、[.vsz ファイル](../ide/dot-vsz-file-project-control.md)で SCRIPT\_COMMON\_PATH をこの共通パスに設定します。  
  
> [!NOTE]
>  Visual C\+\+ に含まれているウィザードでは Common.js の JScript 関数を使用します。  これらの関数を変更すると、Visual C\+\+ のウィザードが予測しない動作をする可能性があります。  
  
 JScript の詳細については、「[Writing, Compiling, and Debugging JScript Code](http://msdn.microsoft.com/ja-jp/13e57e7d-4867-4555-b9e4-fc24aa75e628)」を参照してください。  
  
## スクリプトのデバッグ  
 ウィザードの html ファイルのスクリプトをデバッグするには、スクリプトのデバッグを有効にする必要があります。  
  
#### スクリプトのデバッグを有効にするには  
  
1.  Internet Explorer で、\[ツール\] メニューの **\[インターネット オプション\]** を選択します。  
  
2.  **\[詳細設定\]** タブをクリックします。  
  
3.  \[ブラウズ\] の下の \[スクリプトのデバッグを使用しない\] チェック ボックスをオフにします。  
  
 これで、ウィザードの \[完了\] をクリックすると、common.js と default.js が **\[実行中のドキュメント\]** ウィンドウに表示されます。  
  
## 参照  
 [ウィザード用に作成されるファイル](../ide/files-created-for-your-wizard.md)   
 [カスタム ウィザード](../ide/custom-wizard.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)