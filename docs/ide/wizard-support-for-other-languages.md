---
title: "ウィザードでサポートされるその他の言語 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.EastAsianLanguages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "言語サポート (MFC プロジェクトの)"
  - "プロジェクト [C++], 言語サポート"
  - "ウィザード [C++], 言語サポート"
ms.assetid: b653c673-0687-455c-885f-15d7e2f4149d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ウィザードでサポートされるその他の言語
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio のインストール時には、セットアップ アプリケーションがシステムのロケールを検出し、そのロケールに対応する言語テンプレートをインストールします。  たとえば、西ヨーロッパのロケールの場合は、英語、フランス語、イタリア語、スペイン語、およびドイツ語がインストールされます。  インストールされた言語は、MFC アプリケーション ウィザードの [&#91;アプリケーションの種類&#93;](../Topic/Application%20Type,%20MFC%20Application%20Wizard.md) ページの \[リソース言語\] ボックスに表示されます。  
  
## 言語テンプレート  
 テンプレートは ANSI エンコードに基いており、一部のシステムでは編集できないリソースがあります。このため、システムによってはインストールされないテンプレートがあります。  たとえば、既定では、フランス語のシステムでは日本語のリソースを編集できません。  
  
 Windows 2000 以降を使用して他の言語で MFC アプリケーションを作成する場合は、Visual Studio インストーラー メディア\(ディスク 1\) にある適切な言語のテンプレート ディレクトリをシステムにコピーする必要があります。  
  
> [!NOTE]
>  作成したプロジェクトを編集するには、選択した言語に対応するロケールにシステムのロケールを変更する必要があります。  
  
 次の表に示すように、各テンプレートに対して、\\Microsoft Visual Studio .NET 2003\\Vc7\\VCWizards\\mfcappwiz\\templates\\ ディレクトリのフォルダーが割り当てられています。  使用する言語テンプレートにアクセスするには、該当するフォルダーをコンピューターの \\mfcappwiz\\templates\\ ディレクトリにコピーします。  フォルダーのコピーが完了すると、MFC アプリケーション ウィザードの **\[アプリケーションの種類\]** ページの \[リソース言語\] ボックスにその言語が表示されます。  
  
### Visual Studio .NET で指定されている言語テンプレート  
  
|言語|テンプレート|  
|--------|------------|  
|繁体字中国語|1028|  
|簡体字中国語|2052|  
|英語|1033|  
|フランス語|1036|  
|ドイツ語|1031|  
|イタリア語|1040|  
|日本語|1041|  
|韓国語|1042|  
|スペイン語|3082|  
  
## Visual C\+\+ ウィザードによって生成されるファイル形式  
 Visual C\+\+ ウィザードでは、インストールされた Visual Studio の言語バージョンがシステムのロケールと異なる場合、プロジェクトが Unicode で生成されます。  たとえば、地域設定が日本語以外のコンピューターに対し、日本語版の Visual Studio をインストールした場合、Visual C\+\+ ウィザードでは、Unicode ファイルから成るプロジェクトが生成されます。  これは、Windows マルチ言語 \(MUI\) パックでセットアップされたマシン全般に言えることです。  
  
 システム ロケールが Visual Studio の言語バージョンと同じ場合、これとは異なる動作になります。  プロジェクト ファイルはシステムの ANSI コード ページで生成されます。  
  
## 参照  
 [Visual C\+\+ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Visual C\+\+ プロジェクトの作成および管理](../ide/creating-and-managing-visual-cpp-projects.md)