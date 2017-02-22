---
title: "How to: Change the Language or Condition of a Resource While Copying | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.resvw.resource.changing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Language property"
  - "condition property of resource"
ms.assetid: 8f622ab0-bac2-468f-ae70-78911afc4759
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# How to: Change the Language or Condition of a Resource While Copying
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リソースのコピー時に、リソースの言語プロパティ、条件プロパティ、またはその両方を変更できます。  
  
-   リソースの言語では、そのリソースで使用する言語のみを識別します。  これは、[FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042) で、検索対象のリソースを識別するために使用されます  \(ただし、各言語でテキストに関連していない違いをリソースに含めることができます。たとえば、日本語キーボードのみで動作するアクセラレータや中国語でローカライズされたビルドのみに対応するビットマップなどです\)。  
  
-   リソースの条件とは、リソースの特定のコピーが使用される条件を識別する定義済みのシンボルです。  
  
 リソースの言語と条件は、\[ワークスペース\] ウィンドウで、リソース名の後に、かっこで囲んで表示されます。  次の例では、リソース IDD\_AboutBox が言語として Finnish、条件として XX33 を使用しています。  
  
```  
IDD_AboutBox (Finnish – XX33)  
```  
  
### 既存のリソースをコピーして、そのリソースの言語または条件を変更するには  
  
1.  .rc ファイル内または [&#91;リソース ビュー&#93;](../windows/resource-view-window.md) ウィンドウで、コピーするリソースを右クリックします。  
  
2.  ショートカット メニューの **\[コピーの挿入\]** をクリックします。  
  
3.  **\[リソース コピーの挿入\]** ダイアログ ボックスで、次の操作を行います。  
  
    -   **\[言語\]** リスト ボックスで言語を選択します。  
  
    -   **\[条件\]** ボックスに条件を入力します。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。 マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的リソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 必要条件  
  
 Win32  
  
## 参照  
 [How to: Copy Resources](../windows/how-to-copy-resources.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)