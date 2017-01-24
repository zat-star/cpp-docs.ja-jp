---
title: "Resource Files (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
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
  - "resources [Visual Studio]"
  - ".rc files"
  - "resource files"
  - "resource script files"
  - "resource script files, Win-32 based applications"
  - "resource script files, files updated when editing resources"
  - "resources [Visual Studio], types of resource files"
  - "rct files"
  - "resources [C++]"
  - "rc files"
  - "resource files, types of"
  - ".rct files"
  - "resource script files, unsupported types"
ms.assetid: 4d2b6fcc-07cf-4289-be87-83a60f69533c
caps.latest.revision: 18
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Resource Files (Visual Studio)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  この情報は Windows デスクトップ アプリケーションに適用されます。[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリ内でのリソースについては、「[アプリ リソースの定義](http://msdn.microsoft.com/ja-jp/476ea844-632c-4467-9ce3-966be1350dd4)」をご覧ください。  
>   
>  マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。.NET プログラミング言語のプロジェクトでは、リソース スクリプト ファイルは使用しないため、**ソリューション エクスプローラー**からリソースを開く必要があります。[イメージ エディター](../mfc/image-editor-for-icons.md)と[バイナリ エディター](../mfc/binary-editor.md)を使用して、マネージ プロジェクトのリソース ファイルを操作できます。 編集の対象となるマネージ リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは埋め込みリソースの編集はサポートされていません。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「[チュートリアル: Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」をご覧ください。  
  
 "リソース ファイル" という用語は、次のようなさまざまな種類のファイルを示します。  
  
-   プログラムのリソース スクリプト \(.rc\) ファイル。  
  
-   リソース テンプレート \(.rct\) ファイル。  
  
-   ビットマップ、アイコン、カーソル ファイルなど、スタンドアロン ファイルとして存在し、.rc ファイルから参照される個別のリソース。  
  
-   Resource.h など、開発環境で生成され、.rc ファイルから参照されるヘッダー ファイル。  
  
 リソースは、.exe、.dll、.res ファイルなど、[その他の種類のファイル](../windows/editable-file-types-for-resources.md)にも存在します。 リソースとリソース ファイルはプロジェクト内から操作できます。また、現在のプロジェクトの一部でないリソースとリソース ファイルも操作できます。 また、Visual Studio の開発環境で作成されたのではないリソース ファイルも操作できます。 たとえば、次のように操作できます。  
  
-   入れ子になっていて、条件付きでインクルードされるリソース ファイルの操作。  
  
-   既存のリソースの更新、または Visual C\+\+ 形式への変換。  
  
-   グラフィック リソースを現在のリソース ファイルとの間でインポートまたはエクスポートする。  
  
-   開発環境では変更できない共有または読み取り専用識別子 \(シンボル\) のインクルード。  
  
-   複数のプロジェクト間で共有されるリソースなど、現在のプロジェクトで編集を必要としない \(または編集したくない\) 実行可能 \(.exe\) ファイル内のリソースのインクルード。  
  
-   開発環境でサポートされていない種類のリソースのインクルード。  
  
 ここでは、以下の内容について説明します。  
  
-   [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)  
  
-   [リソースの新規作成](../windows/how-to-create-a-resource.md)  
  
-   [リソース スクリプト ファイル内のリソースの表示](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)  
  
-   [テキスト形式でリソース スクリプト ファイルを開く](../windows/how-to-open-a-resource-script-file-in-text-format.md)  
  
-   [コンパイル時のリソースのインクルード](../Topic/How%20to:%20Include%20Resources%20at%20Compile%20Time.md)  
  
-   [リソースのコピー](../windows/how-to-copy-resources.md)  
  
-   [リソース テンプレート \(.rct\) の使用](../Topic/How%20to:%20Use%20Resource%20Templates.md)  
  
-   [リソースのインポートとエクスポート](../windows/how-to-import-and-export-resources.md)  
  
-   [編集可能なリソース ファイルの種類](../windows/editable-file-types-for-resources.md)  
  
-   [リソース編集の影響を受けるファイル](../Topic/Files%20Affected%20by%20Resource%20Editing.md)  
  
## 必要条件  
 Win32  
  
## 参照  
 [Resource Editors](../mfc/resource-editors.md)   
 [Working with Resource Files](../mfc/working-with-resource-files.md)   
 [メニューとその他のリソース](http://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)