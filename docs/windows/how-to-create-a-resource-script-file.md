---
title: "How to: Create a Resource Script File | Microsoft Docs"
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
  - "rc files, creating"
  - ".rc files, creating"
  - "resource script files, creating"
ms.assetid: 82be732a-cdcd-4a58-8de7-976d1418f86b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# How to: Create a Resource Script File
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  リソース エディターは Express Edition では使用できません。  
>   
>  これは Windows デスクトップ アプリケーションだけに適用できます。 .NET 言語のプロジェクトでは、リソース スクリプト ファイルを使用しません。 詳細については、「[リソース ファイル \(Visual Studio\)](../mfc/resource-files-visual-studio.md)」を参照してください。  
  
### リソース スクリプト \(.rc\) ファイルを新規作成するには  
  
1.  `Solution Explorer` で、"MyProject" などの既存のプロジェクト フォルダーにフォーカスを移します。  
  
    > [!NOTE]
    >  プロジェクト フォルダーをソリューション エクスプローラーの \[ソリューション\] フォルダーと混同しないでください。 \[ソリューション\] フォルダーにフォーカスを移すと、\[新しい項目の追加\] ダイアログ ボックスで選択した項目 \(手順 3\) とは異なった項目になります。  
  
2.  **\[プロジェクト\]** メニューの **\[新しい項目の追加\]** をクリックします。  
  
3.  **\[新しい項目の追加\]** ダイアログ ボックスで、**\[Visual C\+\+\]** フォルダーをクリックし、右側のペインの **\[リソース ファイル \(.rc\)\]** を選択します。  
  
4.  **\[プロジェクト名\]** ボックスにリソース スクリプト ファイルの名前を入力し、**\[開く\]** をクリックします。  
  
 これで、新しいリソースを[作成](../windows/how-to-create-a-resource.md)して .rc ファイルに追加できます。  
  
> [!NOTE]
>  リソース スクリプト \(.rc ファイル\) を追加できるのは、Visual Studio IDE に読み込まれる既存のプロジェクトだけです。 プロジェクトの外側にあるスタンドアロンの .rc ファイルは作成できません。[リソース テンプレート](../Topic/How%20to:%20Use%20Resource%20Templates.md) \(.rct ファイル\) はいつでも作成できます。  
  
 必要条件  
  
 Win32  
  
## 参照  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)