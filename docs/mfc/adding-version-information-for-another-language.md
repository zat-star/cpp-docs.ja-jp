---
title: "Adding Version Information for Another Language | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.version"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "languages, version information"
  - "New Version Info Block"
  - "blocks, adding"
  - "resources [Visual Studio], adding version information"
  - "version information, adding for languages"
ms.assetid: 17f6273c-e1cc-441a-a3d8-f564341cbf20
caps.latest.revision: 14
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Version Information for Another Language
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### 別の言語のバージョン情報 \(新しい情報ブロック\) を追加するには  
  
1.  [&#91;リソース ビュー&#93;](../windows/resource-view-window.md) でバージョン情報リソースをダブルクリックして開きます。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  バージョン情報のテーブル内で右クリックし、ショートカット メニューから **\[新しいバージョン情報ブロック\]** を選びます。  
  
     このコマンドを使用して、現在のバージョン情報リソースにさらに情報ブロックを追加し、それに対応するプロパティを [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)で開きます。  
  
3.  **\[プロパティ\]** ウィンドウで、新しいブロック用の適切な言語と文字セットを選びます。  
  
 マネージ プロジェクトにリソースを追加する方法については、『*.NET Framework 開発者ガイド*』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」をご覧ください。  
  
 **要件**  
  
 Win32  
  
## 参照  
 [Version Information Editor](../mfc/version-information-editor.md)   
 [バージョン情報 \(Windows\)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)