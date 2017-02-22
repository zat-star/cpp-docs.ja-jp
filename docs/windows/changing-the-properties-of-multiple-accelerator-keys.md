---
title: "Changing the Properties of Multiple Accelerator Keys | Microsoft Docs"
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
  - "keyboard shortcuts [C++], property changing"
  - "accelerator tables [C++], changing properties"
ms.assetid: b55c9bd6-b430-48bb-b942-0e6f21d7abf9
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Changing the Properties of Multiple Accelerator Keys
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### 複数のアクセラレータ キーのプロパティを変更するには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)でアイコンをダブルクリックして、アクセラレータ テーブルを開きます。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  **Ctrl** キーを押しながら、変更する各アクセラレータ キーをクリックして選択します。  
  
3.  [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)に移動し、選択したすべてのアクセラレータ キーで共有する値を入力します。  
  
    > [!NOTE]
    >  \[プロパティ\] ウィンドウには、各修飾子の値がブール型のプロパティとして表示されます。  \[プロパティ\] ウィンドウの \[[修飾子&#93;](../windows/accelerator-modifier-property.md) の値を変更すると、アクセラレータ テーブルでは、新しい修飾子が既存の修飾子に対する追加の修飾子として扱われます。  したがって、修飾子の値を設定する場合は、各アクセラレータ キーが同じ \[修飾子\] の設定を共有するように値を設定する必要があります。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 **要件**  
  
 Win32  
  
## 参照  
 [Editing Accelerator Tables](../windows/editing-accelerator-tables.md)   
 [Accelerator Editor](../Topic/Accelerator%20Editor.md)