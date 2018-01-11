---
title: "XML ドキュメント ジェネレーター プロパティ ページ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCXDCMakeTool.ValidateIntelliSense
- VC.Project.VCXDCMakeTool.SuppressStartupBanner
- VC.Project.VCXDCMakeTool.DocumentLibraryDependencies
- VC.Project.VCXDCMakeTool.OutputDocumentFile
- VC.Project.VCXDCMakeTool.AdditionalDocumentFiles
dev_langs: C++
ms.assetid: 645912b5-197a-4c36-ba58-64df09444ca0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bc09dafc0f07bc16a11dd255419440b6464456c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="xml-document-generator-tool-property-pages"></a>[XML ドキュメント ジェネレーター] プロパティ ページ
XML ドキュメント ジェネレーター ツール プロパティ ページでは、xdcmake.exe の機能を公開します。 xdcmake.exe が、ソース コードには、ドキュメントのコメントが含まれている場合に、.xml ファイルに .xdc ファイルをマージし、 [/doc (ドキュメント コメントの処理) (C/C++)](../build/reference/doc-process-documentation-comments-c-cpp.md)が指定されている。 参照してください[ドキュメント コメントとして推奨されるタグ](../ide/recommended-tags-for-documentation-comments-visual-cpp.md)ソース コードをドキュメントのコメントを追加する方法についてです。  
  
> [!NOTE]
>  開発環境 (プロパティ ページ) で xdcmake.exe オプションは、xdcmake.exe をコマンドラインで使用すると、オプションとは異なります。 コマンドラインで xdcmake.exe の使用方法の詳細については、次を参照してください。 [XDCMake リファレンス](../ide/xdcmake-reference.md)です。  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **著作権情報を抑制します。**  
 著作権メッセージを抑制します。  
  
 **追加のドキュメントのファイル**  
 プロジェクト システムは、.xdc ファイルを検索するディレクトリを追加します。 xdcmake は、常に、プロジェクトによって生成される .xdc ファイルを探します。 複数のディレクトリを指定することができます。  
  
 **出力ドキュメント ファイル**  
 出力の .xml ファイルの名前とディレクトリの場所。 参照してください[のビルドのコマンドとプロパティの一般的なマクロ](../ide/common-macros-for-build-commands-and-properties.md)マクロを使用して、ディレクトリの場所を指定する方法についてはします。  
  
 **ドキュメント ライブラリの依存関係**  
 場合は、プロジェクト、ソリューション内の .lib プロジェクトに依存している、現在のプロジェクトの .xml ファイルに .lib プロジェクトから .xdc ファイルを処理できます。  
  
## <a name="see-also"></a>参照  
 [プロパティ ページ](../ide/property-pages-visual-cpp.md)   
 [プロパティ ページ](../ide/property-pages-visual-cpp.md)