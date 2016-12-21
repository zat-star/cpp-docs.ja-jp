---
title: "How to: Create a Resource | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "toolbars [C++], resources"
  - "resource toolbars"
  - "resources [Visual Studio], creating"
ms.assetid: aad44914-9145-45a3-a7d8-9de89b366716
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Create a Resource
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  リソース ビューは Express Edition ではサポートされていません。  
  
### リソース ビューでリソースを新規作成するには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)でフォーカスを .rc ファイルに置き、**\[編集\]** メニューの **\[リソースの追加\]** をクリックするか、またはリソース ビューで .rc ファイルを右クリックし、ショートカット メニューの **\[リソースの追加\]** をクリックします。  
  
     **メモ** プロジェクトに .rc ファイルがまだ含まれていない場合は、「[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  [&#91;リソースの追加&#93; ダイアログ ボックス](../Topic/Add%20Resource%20Dialog%20Box.md)で、プロジェクトに追加するリソースを選択します。  
  
### ソリューション エクスプローラーでリソースを新規作成するには  
  
1.  **ソリューション エクスプローラー**でプロジェクト フォルダーを右クリックし、ショートカット メニューの **\[追加\]**、**\[リソースの追加\]** の順にクリックします。  
  
     プロジェクトに .rc ファイルがない場合は、この手順で作成されます。 その後、この手順を繰り返すと、特定のリソースの種類を新しい .rc ファイルに追加できます。  
  
2.  [&#91;リソースの追加&#93; ダイアログ ボックス](../Topic/Add%20Resource%20Dialog%20Box.md)で、プロジェクトに追加するリソースを選択します。  
  
### クラス ビューでリソースを新規作成するには  
  
1.  [クラス ビュー](http://msdn.microsoft.com/ja-jp/8d7430a9-3e33-454c-a9e1-a85e3d2db925)で、クラスを右クリックし、ショートカット メニューの **\[追加\]**、**\[リソースの追加\]** の順にクリックします。  
  
2.  [&#91;リソースの追加&#93; ダイアログ ボックス](../Topic/Add%20Resource%20Dialog%20Box.md)で、プロジェクトに追加するリソースを選択します。  
  
### \[プロジェクト\] メニューからリソースを新規作成するには  
  
1.  **\[プロジェクト\]** メニューの **\[リソースの追加\]** を選択します。  
  
 リソースを新規作成すると、Visual C\+\+ により IDD\_Dialog1 などの一意の名前が割り当てられます。 関連するリソース エディターまたは[プロパティ ウィンドウ](../Topic/Properties%20Window.md)でリソースのプロパティを編集することによって、このリソース ID をカスタマイズできます。  
  
 リソースは、新しい既定のリソース \(テンプレートに基づいていないリソース\) として作成するか、または[テンプレート](../Topic/How%20to:%20Use%20Resource%20Templates.md)の後でパターン化されるリソースとして作成できます。  
  
 マネージ プロジェクトにリソースを追加する方法については、『*.NET Framework 開発者ガイド*』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。  
  
 **必要条件**  
  
 Win32  
  
## 参照  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)   
 [\[リソースの追加\] ダイアログ ボックス](../Topic/Add%20Resource%20Dialog%20Box.md)