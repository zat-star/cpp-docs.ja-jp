---
title: "How to: Open a Resource Script File in Text Format | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.resource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resource script files, opening in text format"
  - ".rc files, opening in text format"
  - "rc files, opening in text format"
ms.assetid: 0bc57527-f53b-40c9-99a9-4dcbc5c9af57
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# How to: Open a Resource Script File in Text Format
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ダイアログ ボックスなどのリソースをそのリソース固有のリソース エディター内で開くことなく、プロジェクトのリソース スクリプト \(.rc\) ファイルの内容を表示する場合があります。  たとえば、リソース ファイル内のすべてのダイアログ ボックスで文字列を検索する場合に、個別にダイアログ ボックスを開区必要はありません。  
  
> [!NOTE]
>  プロジェクトに .rc ファイルがまだ含まれていない場合は、「[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
 リソース ファイルをテキスト形式で開き、そのファイルに含まれるすべてのリソースを表示したり、[テキスト エディター](http://msdn.microsoft.com/ja-jp/508e1f18-99d5-48ad-b5ad-d011b21c6ab1)でサポートされている全体的な操作を実行したりすることは簡単です。  
  
> [!NOTE]
>  リソース エディターは、.rc ファイルや resource.h ファイルを直接読み取りません。  リソース コンパイラがこれらのファイルをコンパイルして、リソース エディターで使用される .aps ファイルにします。  これはコンパイル手順のファイルで、シンボル データのみが格納されます。  通常のコンパイル プロセスと同様に、シンボル以外の情報 \(コメントなど\) はコンパイル プロセス中に破棄されます。  .aps ファイルと .rc ファイルが一致しなくなると、そのたびに .rc ファイルが再生成されます \(たとえば、\[保存\] を実行すると、リソース エディターによって .rc ファイルと resource.h ファイルが上書きされます\)。  リソース自体に対する変更は .rc ファイルに組み込まれたままですが、コメントは .rc ファイルが上書きされると失われます。  コメントを保持する方法については、「[コンパイル時にリソースをインクルードする](../Topic/How%20to:%20Include%20Resources%20at%20Compile%20Time.md)」を参照してください。  
  
### テキスト形式でリソース スクリプト ファイルを開くには  
  
1.  **\[ファイル\]** メニューの **\[開く\]** を選択し、**\[ファイル\]** をクリックします。  
  
2.  **\[ファイルを開く\]** ダイアログ ボックスで、テキスト形式で表示するリソース スクリプト ファイルに移動します。  
  
3.  ファイルを強調表示し、**\[開く\]** ボタンのドロップダウン矢印 \(ボタンの右側にあります\) をクリックします。  
  
4.  ドロップダウン メニューから **\[ファイルを開くアプリケーションの選択\]** を選択します。  
  
5.  **\[ファイルを開くアプリケーションの選択\]** ダイアログ ボックスで、**\[ソース コード \(テキスト\) エディター\]** をクリックします。  
  
6.  **\[用途\]** ボックスの一覧で **\[テキスト\]** を選択します。  
  
     リソースがソース コード エディターで開きます。  
  
 または  
  
1.  **ソリューション エクスプローラー**で .rc ファイルを右クリックします。  
  
2.  ショートカット メニューで **\[ファイルを開くアプリケーションの選択\]** を選択し、**\[ソース コード \(テキスト\) エディター\]** を選択します。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。 マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的リソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 必要条件  
  
 Win32  
  
## 参照  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)