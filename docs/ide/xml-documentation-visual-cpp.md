---
title: "XML に関するドキュメント (Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "C++ ドキュメントの /// 区切り記号"
  - "コメント, C++ ソース コード ファイル"
  - "XML ドキュメント"
  - "XML, ソース コードのドキュメント コメント"
ms.assetid: a1aec1c5-b2d1-4c74-83ae-1dbbbb76b506
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# XML に関するドキュメント (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ では、.xml ファイルに処理される、ソース・コードにコメントを追加できます。  このファイルは、コードのクラスに関するドキュメントを作成するプロセスに、入力があります。  
  
 Visual C\+\+ コード ファイルでは、XML ドキュメント コメントはメソッドまたは型定義前に直接ある必要があります。  コメントは次のシナリオでは、Intellisense QuickInfo のデータのツールヒントの設定に使用できます:  
  
1.  コードを伴う .winmd ファイルを含む Windows のランタイム コンポーネントとしてコンパイルするときは  
  
2.  ソース・コードが現在のプロジェクトに含まれている場合。  
  
3.  型宣言および実装で同じヘッダー ファイルにあるライブラリ  
  
> [!NOTE]
>  現在のリリースでは、テンプレート型 \(たとえば、テンプレートとしてパラメーターを受け取る関数\) を含むテンプレートまたは任意のコード コメントは処理されません。  このようなコメントを追加すると、未定義の動作が発生します。  
  
 ドキュメント コメントによる .xml ファイルの作成の詳細については、次のトピックを参照してください。  
  
|参照する内容|参照項目|  
|------------|----------|  
|使用されるコンパイラ オプション|[\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)|  
|ドキュメントの汎用機能を提供するために使用できるタグ|[ドキュメント コメントとして推奨されるタグ](../Topic/Recommended%20Tags%20for%20Documentation%20Comments%20\(Visual%20C++\).md)|  
|コードの構造を識別するためにコンパイラが生成した ID 文字列|[.xml ファイルの処理](../ide/dot-xml-file-processing.md)|  
|ドキュメント タグを区切る方法|[Visual C\+\+ のドキュメント タグの区切り記号](../ide/delimiters-for-visual-cpp-documentation-tags.md)|  
|.xml を生成する一つ以上のファイルの .xdc ファイルからします。|[XDCMake の参照](../ide/xdcmake-reference.md)|  
|Visual Studio の機能の領域に関連するように、XML に関する情報へのリンク|[Visual Studio の XML](../Topic/XML%20Tools%20in%20Visual%20Studio.md)|  
  
 設定する必要がある場合はドキュメントのテキストの XML の特殊文字をコメント アウトすると、エンティティまたは XML CDATA セクションを使用する必要があります。  
  
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)