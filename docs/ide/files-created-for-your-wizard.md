---
title: "ウィザード用に作成されるファイル | Microsoft Docs"
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
  - "カスタム ウィザード, 削除 (ファイルを)"
  - "カスタム ウィザード, ファイル (作成された)"
  - "ファイル [C++], 作成 (カスタム ウィザードで)"
  - "アイコン, 削除"
ms.assetid: 7f0e393c-395e-491b-add2-904cf8838e81
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ウィザード用に作成されるファイル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

独自のウィザードでは、**\[新しいプロジェクト\]** ダイアログ ボックスの **\[プロジェクト名\]** ボックスで指定した名前を使用して、一部のファイルやクラスの名前を作成します。  
  
 [カスタム ウィザード](../ide/custom-wizard.md)は、独自のウィザード用に作成したファイルにコメントを追加します。  さらに、新しいアプリケーション ディレクトリに readme.txt というテキスト ファイルを作成します。  このファイルは、カスタム ウィザードで作成されたほかの新しいファイルの内容と使い方について説明するファイルです。  
  
 カスタム ウィザードで作成されるファイルを次の表に示します。  ウィザードの作成に必要な要素どうしの関係の詳細については、「[ウィザードのデザイン](../ide/designing-a-wizard.md)」を参照してください。  
  
|File|Description|  
|----------|-----------------|  
|[Project.vsz](../ide/dot-vsz-file-project-control.md)|以前の .ini 形式に似たテキスト ファイルです。  このファイルは、ウィザード エンジンを識別し、コンテキストとオプションの[カスタム パラメーター](../ide/custom-parameters-in-the-wizard-dot-vsz-file.md)を提供します。|  
|[Project.vsdir](../Topic/Adding%20Wizards%20to%20the%20Add%20Item%20and%20New%20Project%20Dialog%20Boxes%20by%20Using%20.Vsdir%20Files.md)|Visual Studio Shell でウィザードを検索して **\[新しいプロジェクト\]** ダイアログ ボックスに表示できるようにするためのテキスト ファイルです。|  
|[HTML ファイル \(オプション\)](../ide/html-files.md)|ウィザードには、ユーザー インターフェイス \(UI: User Interface\)、つまり HTML インターフェイスを含めることができます。  UI のないウィザードには HTML ファイルは含まれません。<br /><br /> ウィザードに UI がある場合、ウィザード内の各画面は "*ページ*" と呼ばれ、各ページが UI の機能を指定します。<br /><br /> default.htm ファイルは、ウィザードの最初のページを定義します。  追加のページを指定するには、[&#91;アプリケーションの設定&#93; \(カスタム ウィザード\)](../Topic/Application%20Settings,%20Custom%20Wizard.md) の **\[ページ数\]** ボックスを使用します。  追加の各ページは、Page\_\<ページ番号\>.htm ファイルによって定義されます。\<ページ番号\> の範囲は、2 から指定したページ数までです。|  
|[スクリプト ファイル](../ide/jscript-file.md)|カスタム ウィザードは、作成された各ウィザードに対して JScript ファイル default.js を作成します。  このファイルには、Visual C\+\+ ウィザード モデル、コード モデル、および環境オブジェクト モデルにアクセスしてウィザードをカスタマイズする、JScript 関数が含まれます。  ウィザードの default.js ファイルで、関数をカスタマイズしたり追加したりできます。<br /><br /> ウィザードには [common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md) ファイルも追加されます。このファイルには頻繁に使用される JScript 関数が含まれており、他の種類のプロジェクトを作成するために Visual C\+\+ が使用するウィザードも含め、すべてのウィザードで共有されます。  詳細については、「[共通の JScript 関数による C\+\+ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)」を参照してください。|  
|[テンプレート](../ide/template-files.md)|ウィザードのテンプレートは、ディレクティブを含むテキスト ファイルの集まりです。これらのディレクティブは、ウィザード ユーザーの選択に応じて、解析されてからシンボル テーブルに挿入されます。  テンプレート テキスト ファイルは、ユーザーの入力に従ってレンダリングされ、ウィザードで作成したプロジェクトに追加されます。  ウィザード コントロールのシンボル テーブルに直接アクセスすることによって、適切な情報が取得されます。|  
|[Templates.inf](../Topic/Templates.inf%20File.md)|プロジェクトに関連付けられているすべてのテンプレートを一覧表示するテキスト ファイルです。|  
|Default.vcxproj|プロジェクトの種類に関する情報が含まれている .xml ファイルです。|  
|Sample.txt|ウィザードのディレクティブの使い方を示すテンプレート ファイルです。|  
|ReadMe.txt|カスタム ウィザードで作成された各ファイルの概要が含まれているテンプート ファイルです。|  
|イメージ \(オプション\)|ウィザードの UI を拡張するために、アイコン、GIF、BMP、HTML でサポートされているその他のイメージなど、任意のイメージを指定できます。  UI のないウィザードにはイメージは不要です。|  
|Styles.css \(オプション\)|UI のスタイルを定義するファイルです。  ウィザードにユーザー インターフェイスがない場合、カスタム ウィザードで .css ファイルは作成されません。|  
  
 ウィザードのファイルとディレクトリを削除する場合は、\\vc7\\vcprojects\\ ディレクトリから次のファイルも削除する必要があります。  これらのファイルを削除しない限り、**\[新しいプロジェクト\]** ダイアログ ボックスにウィザードのアイコンが表示されたままになります。  
  
-   *projectname*.vsz  
  
-   *projectname*.ico  
  
-   *projectname*.vsdir  
  
## 参照  
 [カスタム ウィザード](../ide/custom-wizard.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)   
 [共通の JScript 関数による C\+\+ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)