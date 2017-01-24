---
title: "Resource Editors | Microsoft Docs"
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
  - "vs.editors.resource"
  - "vc.resvw.resource.editors"
  - "vs.resvw.resource.editors"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "editors [C++], resource"
  - "editors [C++]"
  - "resource editors"
  - "Windows [C++], application resource editing"
ms.assetid: e20a29ec-d6fb-4ead-98f3-431a0e23aaaf
caps.latest.revision: 16
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Resource Editors
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リソース エディターとは、Visual Studio プロジェクトに含まれているリソースを作成または変更するための特殊な環境です。 Visual Studio のリソース エディターでは、アプリケーションのリソースをすばやく簡単に作成して変更できるようにする技術とインターフェイスを共有します。 リソース エディターを使用すると、[リソースを適切なエディターで表示して編集](../mfc/viewing-and-editing-resources-in-a-resource-editor.md)でき、[リソースをプレビュー](../mfc/previewing-resources.md)することができます。  
  
 リソースを作成したり開いたりすると、適切なエディターが自動的に開きます。  
  
 **注** マネージ プロジェクトでは、リソース スクリプト ファイルは使用しないため、**ソリューション エクスプローラー**からリソースを開く必要があります。[イメージ エディター](../mfc/image-editor-for-icons.md)と[バイナリ エディター](../mfc/binary-editor.md)を使用して、マネージ プロジェクトのリソース ファイルを操作できます。 編集の対象となるマネージ リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。  
  
 マネージ プロジェクトにリソースを追加する方法については、『*.NET Framework 開発者ガイド*』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」をご覧ください。  
  
|使用|編集|  
|--------|--------|  
|[アクセラレータ エディター](../Topic/Accelerator%20Editor.md)|アクセラレータ テーブル \(Visual C\+\+ プロジェクトでの\)|  
|[バイナリ エディター](../mfc/binary-editor.md)|Visual C\+\+、Visual Basic、または Visual C\# プロジェクトのバイナリ データの情報およびカスタム リソース。|  
|[ダイアログ エディター](../mfc/dialog-editor.md)|ダイアログ ボックス \(Visual C\+\+ プロジェクトでの\)|  
|[HTML デザイナー](../Topic/HTML%20Designer.md)|デザイン ビューと HTML ビューの両方の HTML ページ。 注意: EXE または DLL 内にある HTML ページは変更できません。変更内容が EXE または DLL にインポートで戻されないためです。|  
|[イメージ エディター](../mfc/image-editor-for-icons.md)|Visual C\+\+、Visual Basic、または Visual C\# プロジェクトのビットマップ、アイコン、カーソル、およびその他のイメージ ファイル。|  
|[メニュー エディター](../Topic/Menu%20Editor.md)|Visual C\+\+ プロジェクトのメニュー リソース。|  
|[Ribbon エディター](../mfc/ribbon-designer-mfc.md)|MFC プロジェクトのリボン リソース。|  
|[ストリング エディター](../mfc/string-editor.md)|文字列テーブル \(Visual C\+\+ プロジェクトでの\)|  
|[ツール バー エディター](../mfc/toolbar-editor.md)|Visual C\+\+ プロジェクトのツール バー リソース。 ツール バー エディターは、イメージ エディターの一部です。|  
|[バージョン エディター](../mfc/version-information-editor.md)|Visual C\+\+ プロジェクトのバージョン情報です。|  
  
## 要件  
 なし  
  
## 参照  
 [Working with Resource Files](../mfc/working-with-resource-files.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)   
 [メニューとその他のリソース](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)