---
title: "How to: Copy Resources | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.resvw.resource.copying"
  - "vs.resvw.resource.copying"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], moving between files"
  - "resources [Visual Studio], copying"
  - "resource files, copying or moving resources between"
  - "resource files, tiling"
  - ".rc files, copying resources between"
  - "rc files, copying resources between"
ms.assetid: 65f523e8-017f-4fc6-82d1-083c56d9131f
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Copy Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リソースを変更せずにファイル間でコピーできます。また、[リソースのコピー時に言語や条件を変更](../windows/how-to-change-the-language-or-condition-of-a-resource-while-copying.md)できます。  
  
 既存のリソース ファイルまたは実行可能ファイルから、現在のリソース ファイルにリソースを簡単にコピーできます。  そのためには、リソースが格納されている両方のファイルを同時に開き、アイテムを一方のファイルから他方にドラッグするか、または 2 つのファイル間でコピーして貼り付けます。  この方法は、リソース スクリプト \(.rc\) ファイル、リソース テンプレート \(.rct\) ファイル、実行可能 \(.exe\) ファイルで使用できます。  
  
> [!NOTE]
>  Visual C\+\+ には、独自のアプリケーションで使用できるサンプルのリソース ファイルが用意されています。  詳細については、「[CLIPART サンプル : コモン リソース](http://msdn.microsoft.com/ja-jp/9bac2891-b6b3-49ec-a287-cec850c707e0)」を参照してください。  
  
 [プロジェクトの外側](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)で開いている .rc ファイル間では、ドラッグ アンド ドロップ機能を使用できます。  
  
### ドラッグ アンド ドロップ機能を使用してファイル間でリソースをコピーするには  
  
1.  両方のリソース ファイルをスタンドアロンで開きます。詳細については、「[プロジェクトの外側にある \(スタンドアロン\) リソース スクリプト ファイルのオープン](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)」を参照してください。  たとえば、Source1.rc と Source2.rc を開きます。  
  
2.  最初の .rc ファイル内で、コピーするリソースをクリックします。  たとえば、Source1.rc 内で IDD\_DIALOG1 をクリックします。  
  
3.  **Ctrl** キーを押しながら、選択したリソースを 2 番目の .rc ファイルにドラッグします。  たとえば、IDD\_DIALOG1 を Source1.rc から Source2.rc にドラッグします。  
  
    > [!NOTE]
    >  Ctrl キーを押さずにリソースをドラッグすると、リソースはコピーされずに移動します。  
  
### コピーと貼り付けを使用してリソースをコピーするには  
  
1.  両方のリソース ファイルをスタンドアロンで開きます。詳細については、「[プロジェクトの外側にある \(スタンドアロン\) リソース スクリプト ファイルのオープン](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)」を参照してください。  たとえば、Source1.rc と Source2.rc を開きます。  
  
2.  Source1.rc など、リソースのコピー元のソース ファイル内で、リソースを右クリックし、ショートカット メニューの \[コピー\] をクリックします。  
  
3.  Source2.rc など、貼り付け先のリソース ファイル内の目的の場所で右クリックします。  ショートカット メニューの \[貼り付け\] をクリックします。  
  
    > [!NOTE]
    >  プロジェクト \(リソース ビュー\) 内のリソース ファイルとスタンドアロンの .rc ファイル \(ドキュメント ウィンドウで開いているファイル\) の間では、ドラッグ アンド ドロップ、コピー、切り取り、貼り付けはできません。  製品の旧バージョンでは、これらの操作ができます。  
  
    > [!NOTE]
    >  新しいファイルにリソースをコピーすると、既存のファイルにあるシンボル名や値との競合を回避するために、転送されたリソースのシンボル値またはシンボル名と値が Visual C\+\+ によって変更されることがあります。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 要件  
  
 Win32  
  
## 参照  
 [How to: Open a Resource Script File Outside of a Project \(Standalone\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)